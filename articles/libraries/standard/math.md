---
title: 'Bibliotecas de Q # Standard: Math | Microsoft Docs'
description: 'Bibliotecas estándar de Q #: matemáticas'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184464"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="fa9a5-103">Funciones matemáticas clásicas</span><span class="sxs-lookup"><span data-stu-id="fa9a5-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="fa9a5-104">Estas funciones se usan principalmente para trabajar con los tipos de datos integrados de Q # `Int`, `Double`y `Range`.</span><span class="sxs-lookup"><span data-stu-id="fa9a5-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="fa9a5-105">La operación <xref:microsoft.quantum.intrinsic.random> tiene `(Double[] => Int)`de firma.</span><span class="sxs-lookup"><span data-stu-id="fa9a5-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="fa9a5-106">Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como un `Int`.</span><span class="sxs-lookup"><span data-stu-id="fa9a5-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="fa9a5-107">La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice.</span><span class="sxs-lookup"><span data-stu-id="fa9a5-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="fa9a5-108">n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.</span><span class="sxs-lookup"><span data-stu-id="fa9a5-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="fa9a5-109">Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="fa9a5-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>