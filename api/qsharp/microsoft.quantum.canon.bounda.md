---
uid: Microsoft.Quantum.Canon.BoundA
title: Función bounda
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728924"
---
# <a name="bounda-function"></a><span data-ttu-id="6155e-102">Función bounda</span><span class="sxs-lookup"><span data-stu-id="6155e-102">BoundA function</span></span>

<span data-ttu-id="6155e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6155e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6155e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6155e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6155e-105">Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.</span><span class="sxs-lookup"><span data-stu-id="6155e-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="6155e-106">El modificador `A` indica que todas las operaciones de la matriz son adjointable.</span><span class="sxs-lookup"><span data-stu-id="6155e-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="6155e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="6155e-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="6155e-108">operaciones: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="6155e-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="6155e-109">Secuencia de operaciones que se va a realizar en una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="6155e-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="6155e-110">Salida: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6155e-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="6155e-111">Nueva operación que realiza cada operación dada en secuencia en su entrada.</span><span class="sxs-lookup"><span data-stu-id="6155e-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6155e-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="6155e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6155e-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="6155e-113">'T</span></span>

<span data-ttu-id="6155e-114">Destino en el que actúa cada una de las operaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="6155e-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="6155e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6155e-115">See Also</span></span>

- [<span data-ttu-id="6155e-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="6155e-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)