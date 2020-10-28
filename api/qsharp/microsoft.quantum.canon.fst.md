---
uid: Microsoft.Quantum.Canon.Fst
title: FST (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728708"
---
# <a name="fst-function"></a><span data-ttu-id="ae98b-102">FST (función)</span><span class="sxs-lookup"><span data-stu-id="ae98b-102">Fst function</span></span>

<span data-ttu-id="ae98b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ae98b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ae98b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae98b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae98b-105">Dado un par, devuelve su primer elemento.</span><span class="sxs-lookup"><span data-stu-id="ae98b-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="ae98b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ae98b-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="ae98b-107">pair: (' t, ' U)</span><span class="sxs-lookup"><span data-stu-id="ae98b-107">pair : ('T,'U)</span></span>

<span data-ttu-id="ae98b-108">Una tupla con dos elementos.</span><span class="sxs-lookup"><span data-stu-id="ae98b-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="ae98b-109">Salida: ' t</span><span class="sxs-lookup"><span data-stu-id="ae98b-109">Output : 'T</span></span>

<span data-ttu-id="ae98b-110">Primer elemento de `pair`.</span><span class="sxs-lookup"><span data-stu-id="ae98b-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ae98b-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ae98b-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ae98b-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="ae98b-112">'T</span></span>

<span data-ttu-id="ae98b-113">Tipo del primer miembro del par.</span><span class="sxs-lookup"><span data-stu-id="ae98b-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="ae98b-114">' U</span><span class="sxs-lookup"><span data-stu-id="ae98b-114">'U</span></span>

<span data-ttu-id="ae98b-115">Tipo del segundo miembro del par.</span><span class="sxs-lookup"><span data-stu-id="ae98b-115">The type of the pair's second member.</span></span>