---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 259296f397207cde4a7d6dfe6cfb1a18e8055216
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211107"
---
# <a name="argcomplex-function"></a><span data-ttu-id="1a2e9-102">ArgComplex función)</span><span class="sxs-lookup"><span data-stu-id="1a2e9-102">ArgComplex function</span></span>

<span data-ttu-id="1a2e9-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1a2e9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1a2e9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1a2e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1a2e9-105">Devuelve la fase de un número complejo de tipo `Complex` .</span><span class="sxs-lookup"><span data-stu-id="1a2e9-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="1a2e9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1a2e9-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="1a2e9-107">entrada: [complejo](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="1a2e9-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="1a2e9-108">Número complejo $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="1a2e9-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="1a2e9-109">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a2e9-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1a2e9-110">Phase $ \text{Arg} [c] = \text{ArcTan} (y, x) \en (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="1a2e9-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>