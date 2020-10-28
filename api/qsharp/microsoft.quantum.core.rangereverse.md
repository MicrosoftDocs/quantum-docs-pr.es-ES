---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727442"
---
# <a name="rangereverse-function"></a>RangeReverse función)

Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Configura [](https://nuget.org/packages/)


Devuelve un nuevo intervalo que es el inverso del intervalo de entrada.

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>Entrada

### <a name="r--range"></a>r: [intervalo](xref:microsoft.quantum.lang-ref.range)

Intervalo de entrada.



## <a name="output--range"></a>Salida: [intervalo](xref:microsoft.quantum.lang-ref.range)

Nuevo intervalo que es el inverso del intervalo especificado.

## <a name="remarks"></a>Observaciones

Tenga en cuenta que el inverso de un intervalo no es simplemente `end` .. `-step` .. `start` , porque el último elemento de un intervalo no puede ser el mismo que `end` .