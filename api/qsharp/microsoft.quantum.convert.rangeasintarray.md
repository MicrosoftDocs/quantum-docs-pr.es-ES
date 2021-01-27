---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850098"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray función)

Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea una matriz `arr` de enteros enumerados por Start.. paso... extremo.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)

`Range`De valores `start..step..end` que se van a convertir en una matriz.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)[]

Nueva matriz de enteros que corresponde a los valores iterados por `range` .

## <a name="example"></a>Ejemplo

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```