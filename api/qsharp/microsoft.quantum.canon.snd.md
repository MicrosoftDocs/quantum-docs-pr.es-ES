---
uid: Microsoft.Quantum.Canon.Snd
title: SND (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852154"
---
# <a name="snd-function"></a><span data-ttu-id="20b60-102">SND (función)</span><span class="sxs-lookup"><span data-stu-id="20b60-102">Snd function</span></span>

<span data-ttu-id="20b60-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20b60-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20b60-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20b60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20b60-105">Dado un par, devuelve su segundo elemento.</span><span class="sxs-lookup"><span data-stu-id="20b60-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="20b60-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="20b60-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="20b60-107">pair: (' t, ' U)</span><span class="sxs-lookup"><span data-stu-id="20b60-107">pair : ('T,'U)</span></span>

<span data-ttu-id="20b60-108">Una tupla con dos elementos.</span><span class="sxs-lookup"><span data-stu-id="20b60-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="20b60-109">Salida: ' U</span><span class="sxs-lookup"><span data-stu-id="20b60-109">Output : 'U</span></span>

<span data-ttu-id="20b60-110">Segundo elemento de `pair` .</span><span class="sxs-lookup"><span data-stu-id="20b60-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="20b60-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="20b60-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20b60-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="20b60-112">'T</span></span>

<span data-ttu-id="20b60-113">Tipo del primer miembro del par.</span><span class="sxs-lookup"><span data-stu-id="20b60-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="20b60-114">' U</span><span class="sxs-lookup"><span data-stu-id="20b60-114">'U</span></span>

<span data-ttu-id="20b60-115">Tipo del segundo miembro del par.</span><span class="sxs-lookup"><span data-stu-id="20b60-115">The type of the pair's second member.</span></span>