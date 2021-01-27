---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Función con particiones
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845538"
---
# <a name="partitioned-function"></a>Función con particiones

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Divide una matriz en varias partes.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Entrada

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)[]

Número de elementos de cada parte de la matriz


### <a name="arr--t"></a>ARR: ' t []

Matriz de entrada que se va a dividir.



## <a name="output--t"></a>Salida: ' t [] []

Varias matrices donde la primera matriz es la primera `nElements[0]` de `arr` y la segunda matriz son las siguientes, `nElements[1]` `arr` etc. La última matriz contendrá todos los elementos restantes.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="example"></a>Ejemplo

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```