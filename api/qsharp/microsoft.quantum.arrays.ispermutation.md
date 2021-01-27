---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848090"
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



## <a name="example"></a>Ejemplo

El siguiente código de r # imprime el mensaje "todos los diagnósticos se completaron correctamente":

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>Observaciones

Una matriz de longitud cero es trivialmente una permutación.