---
title: Usar la Q# biblioteca de valores numéricos de Microsoft
description: Obtenga información sobre los tipos y las operaciones disponibles en la biblioteca de valores numéricos de Microsoft Quantum.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: 474fc74b9c92fbf28c0618a3090905d025699d32
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868804"
---
# <a name="using-the-numerics-library"></a>Usar la biblioteca de valores numéricos

## <a name="overview"></a>Información general

La biblioteca de valores numéricos consta de tres componentes

1. **Aritmética de enteros básico** con agregadores y agregadores de enteros
1. **Funcionalidad de entero de alto nivel** que se basa en la funcionalidad básica; incluye multiplicación, división, inversión, etc.  para enteros con signo y sin signo.
1. **Funcionalidad aritmética de punto fijo** con inicialización de punto fijo, suma, multiplicación, mutua, evaluación polinómica y medición.

Se puede tener acceso a todos estos componentes mediante una sola `open` instrucción:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Tipos

La biblioteca de valores numéricos admite los siguientes tipos

1. **`LittleEndian`**: Una matriz de qubit `qArr : Qubit[]` que representa un entero en `qArr[0]` el que denota el bit menos significativo.
1. **`SignedLittleEndian`**: Igual que, `LittleEndian` salvo que representa un entero con signo almacenado en el complemento de dos.
1. **`FixedPoint`**: Representa un número real que consta de una matriz de qubit `qArr2 : Qubit[]` y una posición de punto binario `pos` , que cuenta el número de dígitos binarios a la izquierda del punto binario. `qArr2`se almacena de la misma manera que `SignedLittleEndian` .

## <a name="operations"></a>Operaciones

Para cada uno de los tres tipos anteriores, hay disponible una variedad de operaciones:

1. **`LittleEndian`**
    - Suma
    - De comparación
    - Multiplicación
    - Elevar
    - División (con resto)

1. **`SignedLittleEndian`**
    - Suma
    - De comparación
    - Complemento del módulo de inversión 2
    - Multiplicación
    - Elevar

1. **`FixedPoint`**
    - Preparación/inicialización en un valor clásico
    - Suma (constante clásica u otro punto fijo Quantum)
    - De comparación
    - Multiplicación
    - Elevar
    - Evaluación polinómica con especialización para las funciones pares e impares
    - Recíproco (1/x)
    - Medida (doble clásico)

Para obtener más información y documentación detallada sobre cada una de estas operaciones, consulte los documentos de referencia de la Q# biblioteca en [docs.Microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>Ejemplo: suma de enteros

Como ejemplo básico, considere la operación $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ es decir, una operación que toma un entero n-qubit $x $ y un valor n-or (n + 1)-qubit registre $y $ como entrada, el último de los cuales se asigna a la suma $ (x + y) $. Tenga en cuenta que la suma es el módulo calculado $2 ^ n $ si $y $ está almacenado en un registro de $-bit $n.

Con el kit de desarrollo de Quantum, esta operación se puede aplicar de la siguiente manera:
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Ejemplo: evaluar funciones fluidas

Para evaluar funciones fluidas como $ \sin (x) $ en un equipo Quantum, donde $x $ es un `FixedPoint` número Quantum, la biblioteca de valores numéricos del kit de desarrollo de Quantum proporciona las operaciones `EvaluatePolynomialFxP` y `Evaluate[Even/Odd]PolynomialFxP` .

La primera, `EvaluatePolynomialFxP` , permite evaluar un polinomio con el formato $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, donde $d $ denota el *grado*. Para ello, lo único que se necesita son los coeficientes polinómicos `[a_0,..., a_d]` (de tipo `Double[]` ), la entrada `x : FixedPoint` y la salida `y : FixedPoint` (inicialmente cero):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
El resultado, $P (x) = 1 + 2x $, se almacenará en `yFxP` .

La segunda, `EvaluateEvenPolynomialFxP` y la tercera,, `EvaluateOddPolynomialFxP` son especializaciones para los casos de las funciones pares e impares, respectivamente. Es decir, para una función par/impar $f (x) $ y $ $ P_ {Even} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, $ $ $f (x) $ se aproxima bien mediante $P _ {Even} (x) $ o $P _ {impares} (x): = x\cdot P_ {Even} (x) $, respectivamente.
En Q# , estos dos casos se pueden administrar de la siguiente manera:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
que evalúa $P _ {Even} (x) = 1 + 2x ^ 2 $ y
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
que evalúa $P _ {impares} (x) = x + 2x ^ 3 $.

## <a name="more-samples"></a>Más ejemplos

Puede encontrar más ejemplos en el [repositorio principal de ejemplos](https://github.com/Microsoft/Quantum).

Para empezar, Clone el repositorio y abra la `Numerics` subcarpeta:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

A continuación, `cd` en una de las carpetas de ejemplo y ejecute el ejemplo a través de

```bash
dotnet run
```
