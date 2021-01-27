---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844532"
---
# <a name="boundca-function"></a><span data-ttu-id="ddf4f-102">BoundCA función)</span><span class="sxs-lookup"><span data-stu-id="ddf4f-102">BoundCA function</span></span>

<span data-ttu-id="ddf4f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ddf4f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ddf4f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddf4f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddf4f-105">Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.</span><span class="sxs-lookup"><span data-stu-id="ddf4f-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="ddf4f-106">El modificador `CA` indica que todas las operaciones de la matriz son adjointable y controlable.</span><span class="sxs-lookup"><span data-stu-id="ddf4f-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ddf4f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="ddf4f-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="ddf4f-108">operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="ddf4f-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="ddf4f-109">Secuencia de operaciones que se va a realizar en una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="ddf4f-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="ddf4f-110">Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="ddf4f-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ddf4f-111">Nueva operación que realiza cada operación dada en secuencia en su entrada.</span><span class="sxs-lookup"><span data-stu-id="ddf4f-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ddf4f-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="ddf4f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ddf4f-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="ddf4f-113">'T</span></span>

<span data-ttu-id="ddf4f-114">Destino en el que actúa cada una de las operaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ddf4f-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="ddf4f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddf4f-115">Example</span></span>

<span data-ttu-id="ddf4f-116">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="ddf4f-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="ddf4f-117">y</span><span class="sxs-lookup"><span data-stu-id="ddf4f-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="ddf4f-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddf4f-118">See Also</span></span>

- [<span data-ttu-id="ddf4f-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="ddf4f-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)