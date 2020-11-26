---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213844"
---
# <a name="rangereverse-function"></a>RangeReverse función)

Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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