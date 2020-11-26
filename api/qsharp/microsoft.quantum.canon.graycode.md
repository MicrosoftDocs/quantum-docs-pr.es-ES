---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206891"
---
# <a name="graycode-function"></a><span data-ttu-id="c4e9f-102">GrayCode función)</span><span class="sxs-lookup"><span data-stu-id="c4e9f-102">GrayCode function</span></span>

<span data-ttu-id="c4e9f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4e9f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4e9f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4e9f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4e9f-105">Crea secuencias de código gris</span><span class="sxs-lookup"><span data-stu-id="c4e9f-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="c4e9f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c4e9f-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="c4e9f-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c4e9f-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c4e9f-108">Número de bits</span><span class="sxs-lookup"><span data-stu-id="c4e9f-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="c4e9f-109">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="c4e9f-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="c4e9f-110">Matriz de tuplas.</span><span class="sxs-lookup"><span data-stu-id="c4e9f-110">Array of tuples.</span></span> <span data-ttu-id="c4e9f-111">El primer valor de la tupla es el valor del segundo valor de la secuencia GrayCode en la tupla es Position para cambiar en el valor actual para obtener el siguiente.</span><span class="sxs-lookup"><span data-stu-id="c4e9f-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>