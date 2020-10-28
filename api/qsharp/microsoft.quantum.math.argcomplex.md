---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732797"
---
# <a name="argcomplex-function"></a>ArgComplex función)

Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Configura [](https://nuget.org/packages/)


Devuelve la fase de un número complejo de tipo `Complex` .

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a>Entrada

### <a name="input--complex"></a>entrada: [complejo](xref:Microsoft.Quantum.Math.Complex)

Número complejo $c = x + i y $.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

Phase $ \text{Arg} [c] = \text{ArcTan} (y, x) \en (-\pi, \pi] $.