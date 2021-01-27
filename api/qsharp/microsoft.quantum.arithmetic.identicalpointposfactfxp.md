---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 7212f918e1d0ee86b12b85caa6e0c27bc2cebe58
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846611"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="3226e-102">IdenticalPointPosFactFxP función)</span><span class="sxs-lookup"><span data-stu-id="3226e-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="3226e-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3226e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3226e-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="3226e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="3226e-105">Declara que todos los números de punto fijo de la matriz proporcionada tienen posiciones de punto idénticas al contar desde el bit menos significativo.</span><span class="sxs-lookup"><span data-stu-id="3226e-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="3226e-106">Es decir, el número de bits menos la posición de punto debe ser constante para todos los números de punto fijo de la matriz.</span><span class="sxs-lookup"><span data-stu-id="3226e-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3226e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="3226e-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="3226e-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="3226e-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="3226e-109">Matriz de números de punto fijo Quantum cuya compatibilidad se comprobará (mediante aserciones).</span><span class="sxs-lookup"><span data-stu-id="3226e-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="3226e-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3226e-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

