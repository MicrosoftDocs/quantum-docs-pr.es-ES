---
uid: Microsoft.Quantum.Canon.Snd
title: SND (función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728391"
---
# <a name="snd-function"></a><span data-ttu-id="5d9ce-102">SND (función)</span><span class="sxs-lookup"><span data-stu-id="5d9ce-102">Snd function</span></span>

<span data-ttu-id="5d9ce-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5d9ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5d9ce-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d9ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d9ce-105">Dado un par, devuelve su segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="5d9ce-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5d9ce-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="5d9ce-107">pair: (' t, ' U)</span><span class="sxs-lookup"><span data-stu-id="5d9ce-107">pair : ('T,'U)</span></span>

<span data-ttu-id="5d9ce-108">Una tupla con dos elementos.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="5d9ce-109">Salida: ' U</span><span class="sxs-lookup"><span data-stu-id="5d9ce-109">Output : 'U</span></span>

<span data-ttu-id="5d9ce-110">Segundo elemento de `pair` .</span><span class="sxs-lookup"><span data-stu-id="5d9ce-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5d9ce-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="5d9ce-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5d9ce-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="5d9ce-112">'T</span></span>

<span data-ttu-id="5d9ce-113">Tipo del primer miembro del par.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="5d9ce-114">' U</span><span class="sxs-lookup"><span data-stu-id="5d9ce-114">'U</span></span>

<span data-ttu-id="5d9ce-115">Tipo del segundo miembro del par.</span><span class="sxs-lookup"><span data-stu-id="5d9ce-115">The type of the pair's second member.</span></span>