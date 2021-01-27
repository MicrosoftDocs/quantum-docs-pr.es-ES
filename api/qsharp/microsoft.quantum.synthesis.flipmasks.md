---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: FlipMasks función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859255"
---
# <a name="flipmasks-function"></a><span data-ttu-id="c9c83-102">FlipMasks función)</span><span class="sxs-lookup"><span data-stu-id="c9c83-102">FlipMasks function</span></span>

<span data-ttu-id="c9c83-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="c9c83-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="c9c83-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9c83-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9c83-105">Por cada unitario de 2 niveles calcula "Flip Mask", que denota qubits, que debe invertirse antes y después de aplicar la puerta 1-qubit correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c9c83-105">For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate.</span></span>
<span data-ttu-id="c9c83-106">Para mayor comodidad, el resultado es 0.</span><span class="sxs-lookup"><span data-stu-id="c9c83-106">For convenience prepends result with 0.</span></span>

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="c9c83-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c9c83-107">Input</span></span>

### <a name="decomposition--complexintint"></a><span data-ttu-id="c9c83-108">descomposición: ([Complex](xref:Microsoft.Quantum.Math.Complex)[] [],[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="c9c83-108">decomposition : ([Complex](xref:Microsoft.Quantum.Math.Complex)[][],[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="allqubitsmask--int"></a><span data-ttu-id="c9c83-109">allQubitsMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9c83-109">allQubitsMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="c9c83-110">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c9c83-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

