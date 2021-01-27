---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: Descomponer función
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855524"
---
# <a name="decomposedon-function"></a>Descomponer función

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Descompone una permutación en una variable

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Descripción

Dada una permutación $ \pi $ ( `perm` ) y un índice $i $ ( `index` ), este método devuelve tres permutaciones $ ((\ pi_l, \ PI_R), \pi ') $ de modo que las imágenes de $ \ pi_l $ y $ \ PI_R $ no cambian bits en sus elementos en índices distintos de $i $ e imágenes de $ \pi ' $ no cambie el bit $i $ en sus elementos.

## <a name="input"></a>Entrada

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>Índice: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Output: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])



## <a name="example"></a>Ejemplo

Suponga que la entrada es Perm = [0, 2, 3, 5, 7, 1, 4, 6] e índice = 0. a continuación, esta función calcula tres permutaciones basadas en la tabla siguiente, que muestra la permutación `perm` en notación binaria con los elementos del grupo a y las imágenes del grupo D.  Las columnas enumeran los índices de bits.

|   Un |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

Todos los valores de los índices que no son iguales a 0 (= índice) se copian de a a B y de D a C.

|   Un |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

A continuación, se coloca un 0 para el primer elemento con un índice vacío en la columna 0 del bloque B y, a continuación, se coloca un 1 en B donde el prefijo coincide (en el primer caso, la otra fila con índices 0 0).
Después, se agrega 1 en la misma fila del bloque C y, a continuación, un 0 para el prefijo correspondiente en el bloque C.  Este proceso se repite hasta que todos los índices se han colocado en la columna 0 en los bloques B y C.

|   Un |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

Podemos leer tres nuevas permutaciones de la tabla:

- $ \ pi_l $ con elementos de A, imágenes en B (izquierda)
- $ \ pi_r $ con elementos en D, imágenes en C (derecha)
- $ \pi ' $ con elementos en B, imágenes en C (resto)

Tenga en cuenta que los valores de bit de diseño no cambian en $ \ pi_l $ y $ \ pi_r $ para los índices 1 y 2, y los valores de bit no cambian para en $ \ pi_ ' $ para el índice 0.  Tenga en cuenta también que $ \ pi_l $ y $ \ PI_R $ deben ser de inverso.

Las permutaciones derivadas y devueltas son: Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] resto = [0, 3, 2, 5, 6, 1, 4, 7]