---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227308"
---
# <a name="squarednorm-function"></a><span data-ttu-id="40c57-102">SquaredNorm función)</span><span class="sxs-lookup"><span data-stu-id="40c57-102">SquaredNorm function</span></span>

<span data-ttu-id="40c57-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="40c57-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="40c57-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40c57-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40c57-105">Devuelve el cuadrado de 2-norma de un vector.</span><span class="sxs-lookup"><span data-stu-id="40c57-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="40c57-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="40c57-106">Description</span></span>

<span data-ttu-id="40c57-107">Devuelve el cuadrado de 2-norma de un vector; es decir, dada una entrada $ \vec{x} $, devuelve $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="40c57-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="40c57-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="40c57-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="40c57-109">matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="40c57-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="40c57-110">Vector cuya norma de 2-normal se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="40c57-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="40c57-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="40c57-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="40c57-112">La norma 2 cuadrada de `array` .</span><span class="sxs-lookup"><span data-stu-id="40c57-112">The squared 2-norm of `array`.</span></span>