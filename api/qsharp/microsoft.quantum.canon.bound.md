---
uid: Microsoft.Quantum.Canon.Bound
title: Función enlazada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207605"
---
# <a name="bound-function"></a><span data-ttu-id="db36a-102">Función enlazada</span><span class="sxs-lookup"><span data-stu-id="db36a-102">Bound function</span></span>

<span data-ttu-id="db36a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="db36a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="db36a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db36a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db36a-105">Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.</span><span class="sxs-lookup"><span data-stu-id="db36a-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="db36a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="db36a-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="db36a-107">operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="db36a-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="db36a-108">Secuencia de operaciones que se va a realizar en una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="db36a-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="db36a-109">Salida: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="db36a-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="db36a-110">Nueva operación que realiza cada operación dada en secuencia en su entrada.</span><span class="sxs-lookup"><span data-stu-id="db36a-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="db36a-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="db36a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db36a-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="db36a-112">'T</span></span>

<span data-ttu-id="db36a-113">Destino en el que actúa cada una de las operaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="db36a-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="db36a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db36a-114">See Also</span></span>

- [<span data-ttu-id="db36a-115">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="db36a-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="db36a-116">Microsoft. Quantum. Canon. Bounda</span><span class="sxs-lookup"><span data-stu-id="db36a-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="db36a-117">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="db36a-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)