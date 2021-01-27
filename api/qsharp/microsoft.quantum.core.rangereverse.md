---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853652"
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