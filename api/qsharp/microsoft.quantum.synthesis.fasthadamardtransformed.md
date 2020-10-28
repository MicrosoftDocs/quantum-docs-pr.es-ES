---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733893"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="8a740-102">FastHadamardTransformed función)</span><span class="sxs-lookup"><span data-stu-id="8a740-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="8a740-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8a740-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8a740-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a740-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a740-105">Calcula la transformación de Hadamard de una función booleana en {-1,1} la codificación mediante el método de yates</span><span class="sxs-lookup"><span data-stu-id="8a740-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="8a740-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8a740-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="8a740-107">FUNC: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8a740-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8a740-108">Tabla de verdad en la {-1,1} codificación</span><span class="sxs-lookup"><span data-stu-id="8a740-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="8a740-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8a740-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8a740-110">Coeficientes espectrales de la función</span><span class="sxs-lookup"><span data-stu-id="8a740-110">Spectral coefficients of the function</span></span>