---
uid: Microsoft.Quantum.Math.ModulusI
title: Función modulus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732700"
---
# <a name="modulusi-function"></a>Función modulus

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Configura [](https://nuget.org/packages/)


Calcula el residuo canónico del `value` módulo `modulus` .

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>Entrada

### <a name="value--int"></a>valor: [int](xref:microsoft.quantum.lang-ref.int)

Valor del que se calcula el residuo


### <a name="modulus--int"></a>módulo: [int](xref:microsoft.quantum.lang-ref.int)

El módulo por el que se toman los residuos, debe ser positivo



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Entero $r $ entre 0 y `modulus - 1` este que `value - r` es divisible por módulo.

## <a name="remarks"></a>Observaciones

Esta función se comporta de forma diferente a cómo `%` se comporta el operador en C# y Q # como en el resultado siempre es un entero positivo entre 0 y `modulus - 1` , incluso si el valor es negativo.