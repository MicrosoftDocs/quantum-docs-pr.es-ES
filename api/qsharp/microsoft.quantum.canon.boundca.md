---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728900"
---
# <a name="boundca-function"></a><span data-ttu-id="9fe23-102">BoundCA función)</span><span class="sxs-lookup"><span data-stu-id="9fe23-102">BoundCA function</span></span>

<span data-ttu-id="9fe23-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9fe23-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9fe23-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fe23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9fe23-105">Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.</span><span class="sxs-lookup"><span data-stu-id="9fe23-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="9fe23-106">El modificador `CA` indica que todas las operaciones de la matriz son adjointable y controlable.</span><span class="sxs-lookup"><span data-stu-id="9fe23-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9fe23-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="9fe23-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="9fe23-108">operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL []</span><span class="sxs-lookup"><span data-stu-id="9fe23-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="9fe23-109">Secuencia de operaciones que se va a realizar en una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="9fe23-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="9fe23-110">Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL + CTL</span><span class="sxs-lookup"><span data-stu-id="9fe23-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9fe23-111">Nueva operación que realiza cada operación dada en secuencia en su entrada.</span><span class="sxs-lookup"><span data-stu-id="9fe23-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9fe23-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="9fe23-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9fe23-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="9fe23-113">'T</span></span>

<span data-ttu-id="9fe23-114">Destino en el que actúa cada una de las operaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="9fe23-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fe23-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9fe23-115">See Also</span></span>

- [<span data-ttu-id="9fe23-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="9fe23-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)