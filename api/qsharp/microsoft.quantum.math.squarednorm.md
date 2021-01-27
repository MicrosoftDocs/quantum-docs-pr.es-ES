---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848211"
---
# <a name="squarednorm-function"></a><span data-ttu-id="473e3-102">SquaredNorm función)</span><span class="sxs-lookup"><span data-stu-id="473e3-102">SquaredNorm function</span></span>

<span data-ttu-id="473e3-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="473e3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="473e3-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="473e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="473e3-105">Devuelve el cuadrado de 2-norma de un vector.</span><span class="sxs-lookup"><span data-stu-id="473e3-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="473e3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="473e3-106">Description</span></span>

<span data-ttu-id="473e3-107">Devuelve el cuadrado de 2-norma de un vector; es decir, dada una entrada $ \vec{x} $, devuelve $ \ sum_i x_i ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="473e3-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="473e3-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="473e3-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="473e3-109">matriz: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="473e3-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="473e3-110">Vector cuya norma de 2-normal se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="473e3-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="473e3-111">Salida: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="473e3-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="473e3-112">La norma 2 cuadrada de `array` .</span><span class="sxs-lookup"><span data-stu-id="473e3-112">The squared 2-norm of `array`.</span></span>