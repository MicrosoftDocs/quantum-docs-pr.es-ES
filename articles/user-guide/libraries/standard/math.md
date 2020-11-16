---
title: 'Matemáticas en las Q# bibliotecas estándar'
description: 'Obtenga información sobre las funciones matemáticas clásicas en las Q# bibliotecas estándar que se utilizan con los tipos de datos integrados.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692066"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="d1e19-103">Funciones matemáticas clásicas</span><span class="sxs-lookup"><span data-stu-id="d1e19-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="d1e19-104">Estas funciones se utilizan principalmente para trabajar con los Q# tipos de datos integrados `Int` , `Double` y `Range` .</span><span class="sxs-lookup"><span data-stu-id="d1e19-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="d1e19-105">La <xref:Microsoft.Quantum.Intrinsic.Random> operación tiene signatura `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="d1e19-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="d1e19-106">Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como `Int` .</span><span class="sxs-lookup"><span data-stu-id="d1e19-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="d1e19-107">La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice.</span><span class="sxs-lookup"><span data-stu-id="d1e19-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="d1e19-108">n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.</span><span class="sxs-lookup"><span data-stu-id="d1e19-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="d1e19-109">Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="d1e19-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
