---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203100"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="df816-102">FastHadamardTransformed función)</span><span class="sxs-lookup"><span data-stu-id="df816-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="df816-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="df816-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="df816-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df816-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df816-105">Calcula la transformación de Hadamard de una función booleana en {-1,1} la codificación mediante el método de yates</span><span class="sxs-lookup"><span data-stu-id="df816-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="df816-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="df816-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="df816-107">FUNC: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="df816-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="df816-108">Tabla de verdad en la {-1,1} codificación</span><span class="sxs-lookup"><span data-stu-id="df816-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="df816-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="df816-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="df816-110">Coeficientes espectrales de la función</span><span class="sxs-lookup"><span data-stu-id="df816-110">Spectral coefficients of the function</span></span>