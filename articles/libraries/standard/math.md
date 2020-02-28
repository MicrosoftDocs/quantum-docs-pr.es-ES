---
title: Matemáticas en las bibliotecas estándar de preguntas y respuestas
description: Obtenga información sobre las funciones matemáticas clásicas en las bibliotecas de preguntas y respuestas estándar que se utilizan con los tipos de datos integrados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906158"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="82070-103">Funciones matemáticas clásicas</span><span class="sxs-lookup"><span data-stu-id="82070-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="82070-104">Estas funciones se usan principalmente para trabajar con los tipos de datos integrados de Q # `Int`, `Double`y `Range`.</span><span class="sxs-lookup"><span data-stu-id="82070-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="82070-105">La operación <xref:microsoft.quantum.intrinsic.random> tiene `(Double[] => Int)`de firma.</span><span class="sxs-lookup"><span data-stu-id="82070-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="82070-106">Toma una matriz de valores double como entrada y devuelve un índice seleccionado aleatoriamente en la matriz como un `Int`.</span><span class="sxs-lookup"><span data-stu-id="82070-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="82070-107">La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice.</span><span class="sxs-lookup"><span data-stu-id="82070-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="82070-108">n los elementos de la matriz que son iguales a cero se omiten y sus índices nunca se devuelven.</span><span class="sxs-lookup"><span data-stu-id="82070-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="82070-109">Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="82070-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
