---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220933"
---
# <a name="ispermutation-function"></a>IsPermutation función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve true si y solo si una matriz determinada representa una permutación.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Descripción

Dada una matriz `array` de longitud `n` , devuelve true solo si cada entero de `0` hasta `n - 1` aparece exactamente una vez en `array` , por `array` lo que se puede interpretar como una permutación en `n` los elementos.

## <a name="input"></a>Entrada

### <a name="permuation--int"></a>permuation: [int](xref:microsoft.quantum.lang-ref.int)[]

Matriz que puede o no representar una permutación.



## <a name="output--bool"></a>Salida: [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>Observaciones

Una matriz de longitud cero es trivialmente una permutación.