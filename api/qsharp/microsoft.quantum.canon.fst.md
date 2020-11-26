---
uid: Microsoft.Quantum.Canon.Fst
title: FST (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206942"
---
# <a name="fst-function"></a><span data-ttu-id="ef668-102">FST (función)</span><span class="sxs-lookup"><span data-stu-id="ef668-102">Fst function</span></span>

<span data-ttu-id="ef668-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef668-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef668-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef668-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef668-105">Dado un par, devuelve su primer elemento.</span><span class="sxs-lookup"><span data-stu-id="ef668-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="ef668-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ef668-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="ef668-107">pair: (' t, ' U)</span><span class="sxs-lookup"><span data-stu-id="ef668-107">pair : ('T,'U)</span></span>

<span data-ttu-id="ef668-108">Una tupla con dos elementos.</span><span class="sxs-lookup"><span data-stu-id="ef668-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="ef668-109">Salida: ' t</span><span class="sxs-lookup"><span data-stu-id="ef668-109">Output : 'T</span></span>

<span data-ttu-id="ef668-110">Primer elemento de `pair`.</span><span class="sxs-lookup"><span data-stu-id="ef668-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ef668-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ef668-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ef668-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="ef668-112">'T</span></span>

<span data-ttu-id="ef668-113">Tipo del primer miembro del par.</span><span class="sxs-lookup"><span data-stu-id="ef668-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="ef668-114">' U</span><span class="sxs-lookup"><span data-stu-id="ef668-114">'U</span></span>

<span data-ttu-id="ef668-115">Tipo del segundo miembro del par.</span><span class="sxs-lookup"><span data-stu-id="ef668-115">The type of the pair's second member.</span></span>