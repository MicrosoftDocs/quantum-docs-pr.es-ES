---
title: Corrección de errores en las Q# bibliotecas estándar
description: Obtenga información sobre cómo usar códigos de corrección de errores en los Q# programas mientras se protege el estado de la qubits.
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8b1f008793281121bc547d1a6ac3b960feb082ab
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868498"
---
# <a name="error-correction"></a>Corrección de errores #

## <a name="introduction"></a>Introducción ##

En informática clásica, si desea proteger un poco de los errores, a menudo es suficiente para representar ese bit por un *bit lógico* repitiendo el bit de datos.
Por ejemplo, supongamos que $ \overline {0} = $0 es la codificación del bit de datos 0, donde usamos una línea por encima de la etiqueta 0 para indicar que es una codificación de un bit en el estado 0.
Si, de igual forma, se permite $ \overline {1} = $111, tenemos un código de repetición simple que protege frente a un error de volteo de un bit.
Es decir, si se voltea cualquiera de los tres bits, se puede recuperar el estado del bit lógico tomando un voto mayoritario.
Aunque la corrección de errores clásicas es un asunto mucho más rico que este ejemplo concreto (se recomienda la [Introducción a la descodificación de la descodificación](https://www.springer.com/us/book/9783540641339)), el código de repetición anterior ya señala a un posible problema al proteger la información de Quantum.
Es decir, el [teorema sin clonación](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implica que, si se mide cada qubit individual y se toma una votación mayoritaria por analogía con el código clásico anterior, se ha perdido la información precisa que se está intentando proteger.

En el valor de Quantum, veremos que la medida es problemática. Todavía podemos implementar la codificación anterior.
Es útil hacerlo para ver cómo se puede generalizar la corrección de errores en el caso de Quantum.
Por lo tanto, Let $ \ket{\overline {0} } = \ket {000} = \ket {0} \otimes \ket \otimes \ket $ y {0} {0} Let $ \ket{\overline {1} } = \ket {111} $.
Después, por linealidad, hemos definido el código de repetición para todas las entradas. por ejemplo, $ \ket{\overline{+}} = (\ket{\overline {0} } + \ket{\overline {1} })/\sqrt {2} = (\ket {000} + \ket {111} )/\sqrt {2} $.
En concreto, si se permite un error de volteo de bits $X _ 1 $ Act en el qubit intermedio, vemos que la corrección necesaria en ambas bifurcaciones es precisamente $X _ 1 _ 1: $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \left (x_1 \ket {000} + x_1 \ket \right {111} ) \\ \\ & = \frac {1} {\sqrt {2} } \left (\ket {010} + \ket {101} \right).
\end{align} $ $

Para ver cómo podemos identificar que este es el caso sin medir el estado que estamos intentando proteger, es útil anotar qué hace cada error de volteo de bits diferente en los Estados lógicos:

| Error $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ |
| $X_0$ | $ \ket {100} $ | $ \ket {011} $ |
| $X _ 1 _ $ | $ \ket {010} $ | $ \ket {101} $ |
| $X _2 $ | $ \ket {001} $ | $ \ket {110} $ |

Con el fin de proteger el estado que estamos codificando, es necesario poder distinguir los tres errores entre sí y la identidad $ \boldone $ sin distinción entre $ \ket{\overline {0} } $ y $ \ket{\overline {1} } $.
Por ejemplo, si se mide $Z _0 $, se obtiene un resultado diferente para $ \ket{\overline {0} } $ y $ \ket{\overline {1} } $ en el caso de no error, de modo que se contrae el estado codificado.
Por otro lado, considere la posibilidad de medir $Z _0 Z_1 $, la paridad de los primeros dos bits en cada estado de base de cálculo.
Recuerde que cada medida de un operador Pauli comprueba qué eigenvalue se corresponde con el estado que se mide, por lo que para cada estado $ \ket{\psi} $ de la tabla anterior, podemos calcular $Z _0 Z_1 \ket{\psi} $ para ver si obtenemos $ \pm\ket{\psi} $.
Tenga en cuenta que $Z _0 Z_1 \ket {000} = \ket {000} $ y que $Z _0 Z_1 \ket {111} = \ket {111} $, para concluir que esta medida hace lo mismo con ambos Estados codificados.
Por otro lado, $Z _0 Z_1 \ket {100} =-\ket {100} $ y $Z _0 Z_1 \ket {011} =-\ket {011} $, por lo que el resultado de la medición de $Z _0 Z_1 $ revela información útil sobre el error que se ha producido.

Para enfatizar esto, se repite la tabla anterior, pero se agregan los resultados de la medición $Z _0 Z_1 $ y $Z _ 1 Z_2 $ en cada fila.
Denotamos los resultados de cada medida por el signo del eigenvalue que se observa, ya sea $ + $ o $-$, que corresponde a los Q# `Result` valores de `Zero` y `One` , respectivamente.

| Error $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ | Resultado de $Z _0 Z_1 $ | Resultado de $Z _ 1 Z_2 $ |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ | $+$ | $+$ |
| $X_0$ | $ \ket {100} $ | $ \ket {011} $ | $-$ | $+$ |
| $X _ 1 _ $ | $ \ket {010} $ | $ \ket {101} $ | $-$ | $-$ |
| $X _2 $ | $ \ket {001} $ | $ \ket {110} $ | $+$ | $-$ |

Por lo tanto, los resultados de las dos medidas determinan de forma exclusiva qué error de volteo de bits se produjo, pero sin revelar ninguna información sobre el estado que hemos codificado.
Llamamos a estos resultados como un *síndrome*y hacen referencia al proceso de asignación de un síndrome de vuelta al error que lo causó como *recuperación*.
En concreto, hacemos hincapié en que la recuperación es un procedimiento de inferencia *clásico* que toma como entrada el síndrome que se produjo y devuelve una receta sobre cómo corregir los errores que se hayan producido.

> [!NOTE]
> El código de volteo de bits anterior solo puede corregirse frente a errores de volteo de bit único; es decir, una `X` operación que actúa en un único qubit.
> `X`Al aplicar a más de un qubit, se asignará $ \ket{\overline {0} } $ a $ \ket{\overline {1} } $ después de la recuperación.
> Del mismo modo, si se aplica una operación de volteo de fase, `Z` se asignará $ \ket{\overline {1} } $ a $-\ket{\overline {1} } $ y, por lo tanto, se asignará $ \ket{\overline{+}} $ a $ \ket{\overline {-} } $.
> En general, se pueden crear códigos para controlar un mayor número de errores y controlar $Z $ errores, así como $X errores $.

La información que podemos describir medidas en la corrección de errores de Quantum que actúan de la misma manera en todos los Estados de código es la esencia del *formalismo de estabilizador*.
La Q# Canon proporciona un marco para describir la codificación y la descodificación de los códigos del estabilizador, y para describir cómo se recupera de los errores.
En esta sección, se describe este marco de trabajo y su aplicación para algunos códigos de corrección de errores de Quantum simples.

> [!TIP]
> Una introducción completa al estabilizador formalismo está fuera del ámbito de esta sección.
> Nos referimos a los lectores interesados en obtener más información sobre [Gottesman 2009](https://arxiv.org/abs/0904.2557).

## <a name="representing-error-correcting-codes-in-no-locq"></a>Representar códigos de corrección de errores enQ# ##

Para ayudar a especificar los códigos de corrección de errores, Q# Canon proporciona varios tipos definidos por el usuario distintos:

- <xref:microsoft.quantum.errorcorrection.logicalregister>`= Qubit[]`: Denota que un registro de qubits debe interpretarse como el bloque de código de un código de corrección de errores.
- <xref:microsoft.quantum.errorcorrection.syndrome>`= Result[]`: Denota que una matriz de resultados de medida debe interpretarse como el síndrome medido en un bloque de código.
- <xref:microsoft.quantum.errorcorrection.recoveryfn>`= (Syndrome -> Pauli[])`: Denota que se debe usar una función *clásica* para interpretar un síndrome y devolver una corrección que se debe aplicar.
- <xref:microsoft.quantum.errorcorrection.encodeop>`= ((Qubit[], Qubit[]) => LogicalRegister)`: Denota que una operación toma qubits que representan datos junto con ancilla qubits actualizado para generar un bloque de código con un código de corrección de errores.
- <xref:microsoft.quantum.errorcorrection.decodeop>`= (LogicalRegister => (Qubit[], Qubit[]))`: Denota que una operación descompone un bloque de código de un error que corrige código en el qubits de datos y el ancilla qubits que se usa para representar la información del síndrome.
- <xref:microsoft.quantum.errorcorrection.syndromemeasop>`= (LogicalRegister => Syndrome)`: Denota una operación que debe usarse para extraer información de síndrome de un bloque de código, sin alterar el estado protegido por el código.

Por último, la Canon proporciona el <xref:microsoft.quantum.errorcorrection.qecc> tipo para recopilar los otros tipos necesarios para definir un código de corrección de errores de Quantum. Asociado con cada código Quantum del estabilizador es la longitud del código $n $, el número $k $ de qubits lógicos y la distancia mínima $d $, que a menudo se agrupan juntos en la notación ⟦ $n $, $k $, $d $ ⟧. Por ejemplo, la <xref:microsoft.quantum.errorcorrection.bitflipcode> función define el código ⟦ 3, 1, 1 ⟧ bit Flip:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Observe que el `QECC` tipo no *not* incluye una función de recuperación.
Esto nos permite cambiar la función de recuperación que se usa para corregir errores sin cambiar la definición del propio código; Esta capacidad es especialmente útil cuando se incorporan comentarios de medidas de caracterización en el modelo asumido por recuperación.

Una vez que se define un código de esta manera, se puede usar la <xref:microsoft.quantum.errorcorrection.recover> operación para recuperarse de errores:

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

Lo exploramos con más detalle en el [ejemplo de código de volteo de bits](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code).

Además del código de volteo de bits, el Q# Canon se proporciona con implementaciones del [código perfecto de cinco qubit](https://arxiv.org/abs/quant-ph/9602019)y el código de [siete qubit](https://arxiv.org/abs/quant-ph/9705052), ambos pueden corregir un error arbitrario de qubit único.
