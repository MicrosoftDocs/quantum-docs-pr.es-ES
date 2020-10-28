---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733804"
---
# <a name="squarednorm-function"></a><span data-ttu-id="893c6-102">SquaredNorm función)</span><span class="sxs-lookup"><span data-stu-id="893c6-102">SquaredNorm function</span></span>

<span data-ttu-id="893c6-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="893c6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="893c6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="893c6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="893c6-105">Devuelve el cuadrado de 2-norma de un vector.</span><span class="sxs-lookup"><span data-stu-id="893c6-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="893c6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="893c6-106">Description</span></span>

<span data-ttu-id="893c6-107">Devuelve el cuadrado de 2-norma de un vector; es decir, dada una entrada $ \vec{x} $, devuelve $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="893c6-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="893c6-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="893c6-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="893c6-109">matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="893c6-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="893c6-110">Vector cuya norma de 2-normal se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="893c6-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="893c6-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="893c6-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="893c6-112">La norma 2 cuadrada de `array` .</span><span class="sxs-lookup"><span data-stu-id="893c6-112">The squared 2-norm of `array`.</span></span>