---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Función con particiones
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730085"
---
# <a name="partitioned-function"></a>Función con particiones

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Configura [](https://nuget.org/packages/)


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

