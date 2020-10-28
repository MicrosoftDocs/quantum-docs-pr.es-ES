---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727413"
---
# <a name="rangestart-function"></a>RangeStart (función)

Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Configura [](https://nuget.org/packages/)


Devuelve el valor inicial definido del intervalo especificado.

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Valor inicial definido del intervalo especificado.

## <a name="remarks"></a>Observaciones

El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.

Tenga en cuenta que el valor inicial definido de un intervalo es el mismo que el primer elemento de la secuencia, a menos que el intervalo especifique una secuencia vacía (por ejemplo, 2.. 1).