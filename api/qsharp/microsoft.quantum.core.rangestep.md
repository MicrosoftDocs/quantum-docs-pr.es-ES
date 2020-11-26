---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213810"
---
# <a name="rangestep-function"></a>RangeStep función)

Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Devuelve el entero que especifica cómo se calcula el siguiente valor de un intervalo.

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>Entrada

### <a name="range--range"></a>intervalo: [intervalo](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Valor de paso definido del intervalo especificado.

## <a name="remarks"></a>Observaciones

El primer elemento de una expresión de rango es `start` , su segundo elemento es `start+step` , el tercer elemento es `start+step+step` , etc., hasta que `end` se pasa.