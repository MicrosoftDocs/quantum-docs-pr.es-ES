---
uid: Microsoft.Quantum.Canon.Angle
title: Función Angle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219420"
---
# <a name="angle-function"></a><span data-ttu-id="2bcaf-102">Función Angle</span><span class="sxs-lookup"><span data-stu-id="2bcaf-102">Angle function</span></span>

<span data-ttu-id="2bcaf-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2bcaf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2bcaf-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2bcaf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2bcaf-105">Devuelve 1, si `index` tiene un número impar de 1s y-1, si `index` tiene un número par de 1s.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="2bcaf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bcaf-106">Description</span></span>

<span data-ttu-id="2bcaf-107">El valor corresponde al signo del coeficiente del Rademacher-Walsh espectro de la variable n y la función para una asignación determinada que decide el ángulo de rotación.</span><span class="sxs-lookup"><span data-stu-id="2bcaf-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="2bcaf-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2bcaf-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="2bcaf-109">Índice: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bcaf-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2bcaf-110">Asignación de entrada como entero (de 0 a 2 ^ n-1)</span><span class="sxs-lookup"><span data-stu-id="2bcaf-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="2bcaf-111">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2bcaf-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

