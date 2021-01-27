---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5809b5463e6bf8ee73d095dfe4eafedfbb5e0702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852913"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="b6d36-102">ArgComplexPolar función)</span><span class="sxs-lookup"><span data-stu-id="b6d36-102">ArgComplexPolar function</span></span>

<span data-ttu-id="b6d36-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b6d36-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b6d36-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b6d36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b6d36-105">Devuelve la fase de un número complejo de tipo `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="b6d36-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="b6d36-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b6d36-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="b6d36-107">entrada: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="b6d36-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="b6d36-108">Número complejo $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="b6d36-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="b6d36-109">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b6d36-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b6d36-110">Phase $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="b6d36-110">Phase $\text{Arg}[c] = t$.</span></span>