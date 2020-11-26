---
uid: Microsoft.Quantum.Canon.Snd
title: SND (función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205327"
---
# <a name="snd-function"></a><span data-ttu-id="6c645-102">SND (función)</span><span class="sxs-lookup"><span data-stu-id="6c645-102">Snd function</span></span>

<span data-ttu-id="6c645-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6c645-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6c645-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6c645-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6c645-105">Dado un par, devuelve su segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="6c645-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="6c645-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6c645-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="6c645-107">pair: (' t, ' U)</span><span class="sxs-lookup"><span data-stu-id="6c645-107">pair : ('T,'U)</span></span>

<span data-ttu-id="6c645-108">Una tupla con dos elementos.</span><span class="sxs-lookup"><span data-stu-id="6c645-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="6c645-109">Salida: ' U</span><span class="sxs-lookup"><span data-stu-id="6c645-109">Output : 'U</span></span>

<span data-ttu-id="6c645-110">Segundo elemento de `pair` .</span><span class="sxs-lookup"><span data-stu-id="6c645-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6c645-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6c645-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6c645-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="6c645-112">'T</span></span>

<span data-ttu-id="6c645-113">Tipo del primer miembro del par.</span><span class="sxs-lookup"><span data-stu-id="6c645-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="6c645-114">' U</span><span class="sxs-lookup"><span data-stu-id="6c645-114">'U</span></span>

<span data-ttu-id="6c645-115">Tipo del segundo miembro del par.</span><span class="sxs-lookup"><span data-stu-id="6c645-115">The type of the pair's second member.</span></span>