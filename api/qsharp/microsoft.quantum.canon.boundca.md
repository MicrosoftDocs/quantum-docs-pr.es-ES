---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216889"
---
# <a name="boundca-function"></a><span data-ttu-id="29290-102">BoundCA función)</span><span class="sxs-lookup"><span data-stu-id="29290-102">BoundCA function</span></span>

<span data-ttu-id="29290-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="29290-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="29290-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="29290-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="29290-105">Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.</span><span class="sxs-lookup"><span data-stu-id="29290-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="29290-106">El modificador `CA` indica que todas las operaciones de la matriz son adjointable y controlable.</span><span class="sxs-lookup"><span data-stu-id="29290-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="29290-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="29290-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="29290-108">operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL []</span><span class="sxs-lookup"><span data-stu-id="29290-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="29290-109">Secuencia de operaciones que se va a realizar en una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="29290-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="29290-110">Salida: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="29290-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="29290-111">Nueva operación que realiza cada operación dada en secuencia en su entrada.</span><span class="sxs-lookup"><span data-stu-id="29290-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="29290-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="29290-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="29290-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="29290-113">'T</span></span>

<span data-ttu-id="29290-114">Destino en el que actúa cada una de las operaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="29290-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="29290-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29290-115">See Also</span></span>

- [<span data-ttu-id="29290-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="29290-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)