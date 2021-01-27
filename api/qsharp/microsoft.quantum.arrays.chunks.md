---
uid: Microsoft.Quantum.Arrays.Chunks
title: Función fragmentos
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842874"
---
# <a name="chunks-function"></a>Función fragmentos

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Divide una matriz en varias partes de la misma longitud.

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Entrada

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)

La longitud de cada fragmento.


### <a name="arr--t"></a>ARR: ' t []

Matriz que se va a dividir.



## <a name="output--t"></a>Salida: ' t [] []

Una matriz que contiene cada fragmento de la matriz original.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

Tenga en cuenta que el último elemento de la salida puede ser más corto que `nElements` si `Length(arr)` no es divisible por `nElements` .