---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728697"
---
# <a name="graycode-function"></a><span data-ttu-id="3e7c9-102">GrayCode función)</span><span class="sxs-lookup"><span data-stu-id="3e7c9-102">GrayCode function</span></span>

<span data-ttu-id="3e7c9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3e7c9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3e7c9-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e7c9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e7c9-105">Crea secuencias de código gris</span><span class="sxs-lookup"><span data-stu-id="3e7c9-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="3e7c9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3e7c9-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="3e7c9-107">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e7c9-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e7c9-108">Número de bits</span><span class="sxs-lookup"><span data-stu-id="3e7c9-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="3e7c9-109">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="3e7c9-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="3e7c9-110">Matriz de tuplas.</span><span class="sxs-lookup"><span data-stu-id="3e7c9-110">Array of tuples.</span></span> <span data-ttu-id="3e7c9-111">El primer valor de la tupla es el valor del segundo valor de la secuencia GrayCode en la tupla es Position para cambiar en el valor actual para obtener el siguiente.</span><span class="sxs-lookup"><span data-stu-id="3e7c9-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>