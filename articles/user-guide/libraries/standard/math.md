---
title: Matemáticas en las Q# bibliotecas estándar
description: Obtenga información sobre las funciones matemáticas clásicas en las Q# bibliotecas estándar que se utilizan con los tipos de datos integrados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868430"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="64dbd-103">Funciones matemáticas clásicas</span><span class="sxs-lookup"><span data-stu-id="64dbd-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="64dbd-104">Estas funciones se utilizan principalmente para trabajar con los Q# tipos de datos integrados `Int` , `Double` y `Range` .</span><span class="sxs-lookup"><span data-stu-id="64dbd-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="64dbd-105">La <xref:microsoft.quantum.intrinsic.random> operación tiene signatura `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="64dbd-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="64dbd-106">Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como `Int` .</span><span class="sxs-lookup"><span data-stu-id="64dbd-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="64dbd-107">La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice.</span><span class="sxs-lookup"><span data-stu-id="64dbd-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="64dbd-108">n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.</span><span class="sxs-lookup"><span data-stu-id="64dbd-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="64dbd-109">Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="64dbd-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
