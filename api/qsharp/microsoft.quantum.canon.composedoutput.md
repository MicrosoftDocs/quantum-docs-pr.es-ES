---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207469"
---
# <a name="composedoutput-function"></a><span data-ttu-id="2535e-102">ComposedOutput función)</span><span class="sxs-lookup"><span data-stu-id="2535e-102">ComposedOutput function</span></span>

<span data-ttu-id="2535e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2535e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2535e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2535e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2535e-105">Devuelve el resultado de la composición de `inner` y `outer` para una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="2535e-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="2535e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2535e-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="2535e-107">Outer: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="2535e-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="2535e-108">interno: ' U ' > ' U</span><span class="sxs-lookup"><span data-stu-id="2535e-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="2535e-109">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="2535e-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="2535e-110">Salida: ' V</span><span class="sxs-lookup"><span data-stu-id="2535e-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2535e-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2535e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2535e-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="2535e-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="2535e-113">' U</span><span class="sxs-lookup"><span data-stu-id="2535e-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="2535e-114">' V</span><span class="sxs-lookup"><span data-stu-id="2535e-114">'V</span></span>

