---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855450"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="8c21b-102">FastHadamardTransformed función)</span><span class="sxs-lookup"><span data-stu-id="8c21b-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="8c21b-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="8c21b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="8c21b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8c21b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8c21b-105">Calcula la transformación de Hadamard de una función booleana en {-1,1} la codificación mediante el método de yates</span><span class="sxs-lookup"><span data-stu-id="8c21b-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="8c21b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8c21b-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="8c21b-107">FUNC: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8c21b-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8c21b-108">Tabla de verdad en la {-1,1} codificación</span><span class="sxs-lookup"><span data-stu-id="8c21b-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="8c21b-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8c21b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8c21b-110">Coeficientes espectrales de la función</span><span class="sxs-lookup"><span data-stu-id="8c21b-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="8c21b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c21b-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```