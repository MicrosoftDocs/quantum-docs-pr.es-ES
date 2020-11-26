---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 7088397bd60e2779ef60afc1bb7108d937a62c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195773"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="0c65a-102">ArgComplexPolar función)</span><span class="sxs-lookup"><span data-stu-id="0c65a-102">ArgComplexPolar function</span></span>

<span data-ttu-id="0c65a-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0c65a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0c65a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c65a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c65a-105">Devuelve la fase de un número complejo de tipo `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="0c65a-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="0c65a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0c65a-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="0c65a-107">entrada: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="0c65a-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="0c65a-108">Número complejo $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="0c65a-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="0c65a-109">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0c65a-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0c65a-110">Phase $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="0c65a-110">Phase $\text{Arg}[c] = t$.</span></span>