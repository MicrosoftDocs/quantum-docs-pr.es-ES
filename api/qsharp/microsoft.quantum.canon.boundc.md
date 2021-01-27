---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841041"
---
# <a name="boundc-function"></a><span data-ttu-id="c9587-102">BoundC función)</span><span class="sxs-lookup"><span data-stu-id="c9587-102">BoundC function</span></span>

<span data-ttu-id="c9587-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9587-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9587-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c9587-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c9587-105">Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.</span><span class="sxs-lookup"><span data-stu-id="c9587-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="c9587-106">El modificador `C` indica que todas las operaciones de la matriz se pueden controlar.</span><span class="sxs-lookup"><span data-stu-id="c9587-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c9587-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c9587-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="c9587-108">operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL []</span><span class="sxs-lookup"><span data-stu-id="c9587-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="c9587-109">Secuencia de operaciones que se va a realizar en una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="c9587-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="c9587-110">Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="c9587-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c9587-111">Nueva operación que realiza cada operación dada en secuencia en su entrada.</span><span class="sxs-lookup"><span data-stu-id="c9587-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c9587-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c9587-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9587-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="c9587-113">'T</span></span>

<span data-ttu-id="c9587-114">Destino en el que actúa cada una de las operaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c9587-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="c9587-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9587-115">Example</span></span>

<span data-ttu-id="c9587-116">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="c9587-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

<span data-ttu-id="c9587-117">y</span><span class="sxs-lookup"><span data-stu-id="c9587-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="c9587-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9587-118">See Also</span></span>

- [<span data-ttu-id="c9587-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="c9587-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)