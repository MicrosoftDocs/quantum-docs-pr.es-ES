---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727497"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Configura [](https://nuget.org/packages/)


Crea una matriz `arr` de enteros enumerados por Start.. paso... extremo.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)

`Range`De valores `start..step..end` que se van a convertir en una matriz.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)[]

Nueva matriz de enteros que corresponde a los valores iterados por `range` .