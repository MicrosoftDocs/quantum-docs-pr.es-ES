---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223058"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="158e3-102">IdenticalPointPosFactFxP función)</span><span class="sxs-lookup"><span data-stu-id="158e3-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="158e3-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="158e3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="158e3-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="158e3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="158e3-105">Declara que todos los números de punto fijo de la matriz proporcionada tienen posiciones de punto idénticas al contar desde el bit menos significativo.</span><span class="sxs-lookup"><span data-stu-id="158e3-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="158e3-106">Es decir, el número de bits menos la posición de punto debe ser constante para todos los números de punto fijo de la matriz.</span><span class="sxs-lookup"><span data-stu-id="158e3-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="158e3-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="158e3-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="158e3-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="158e3-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="158e3-109">Matriz de números de punto fijo Quantum cuya compatibilidad se comprobará (mediante aserciones).</span><span class="sxs-lookup"><span data-stu-id="158e3-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="158e3-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="158e3-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

