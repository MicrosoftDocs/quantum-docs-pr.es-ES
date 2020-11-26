---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 90a9e31bf5c4a5e92a35998ddaec8c9e9de9888e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224044"
---
# <a name="rangeend-function"></a>RangeEnd función)

Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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