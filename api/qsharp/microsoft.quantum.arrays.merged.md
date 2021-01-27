---
uid: Microsoft.Quantum.Arrays.Merged
title: Función combinada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845609"
---
# <a name="merged-function"></a>Función combinada

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dadas dos matrices ordenadas, devuelve una matriz única que contiene los elementos de ambos en orden. Utilizado internamente por orden de combinación.

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>Entrada

### <a name="comparison--tt---bool"></a>comparación: (' t, ')-> [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>Left: ' t []




### <a name="right--t"></a>Right: ' t []





## <a name="output--t"></a>Salida: ' t []



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

