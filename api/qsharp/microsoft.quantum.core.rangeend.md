---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727448"
---
# <a name="rangeend-function"></a>RangeEnd función)

Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Configura [](https://nuget.org/packages/)


Devuelve el valor final definido del intervalo especificado, que no es necesariamente el último elemento de la secuencia.

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Valor final definido del intervalo especificado.

## <a name="remarks"></a>Observaciones

El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.

Tenga en cuenta que el valor final definido de un intervalo puede diferir del último elemento de la secuencia especificada por el intervalo; por ejemplo, en un intervalo de 0.. 2.. 5 el último elemento es 4, pero el valor final es 5.