---
uid: Microsoft.Quantum.Canon.Fst
title: FST (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840516"
---
# <a name="fst-function"></a><span data-ttu-id="523b1-102">FST (función)</span><span class="sxs-lookup"><span data-stu-id="523b1-102">Fst function</span></span>

<span data-ttu-id="523b1-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="523b1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="523b1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="523b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="523b1-105">Dado un par, devuelve su primer elemento.</span><span class="sxs-lookup"><span data-stu-id="523b1-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="523b1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="523b1-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="523b1-107">pair: (' t, ' U)</span><span class="sxs-lookup"><span data-stu-id="523b1-107">pair : ('T,'U)</span></span>

<span data-ttu-id="523b1-108">Una tupla con dos elementos.</span><span class="sxs-lookup"><span data-stu-id="523b1-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="523b1-109">Salida: ' t</span><span class="sxs-lookup"><span data-stu-id="523b1-109">Output : 'T</span></span>

<span data-ttu-id="523b1-110">Primer elemento de `pair`.</span><span class="sxs-lookup"><span data-stu-id="523b1-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="523b1-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="523b1-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="523b1-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="523b1-112">'T</span></span>

<span data-ttu-id="523b1-113">Tipo del primer miembro del par.</span><span class="sxs-lookup"><span data-stu-id="523b1-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="523b1-114">' U</span><span class="sxs-lookup"><span data-stu-id="523b1-114">'U</span></span>

<span data-ttu-id="523b1-115">Tipo del segundo miembro del par.</span><span class="sxs-lookup"><span data-stu-id="523b1-115">The type of the pair's second member.</span></span>