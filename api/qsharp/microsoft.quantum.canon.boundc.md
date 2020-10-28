---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728913"
---
# <a name="boundc-function"></a><span data-ttu-id="25e11-102">BoundC función)</span><span class="sxs-lookup"><span data-stu-id="25e11-102">BoundC function</span></span>

<span data-ttu-id="25e11-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="25e11-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="25e11-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25e11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25e11-105">Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.</span><span class="sxs-lookup"><span data-stu-id="25e11-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="25e11-106">El modificador `C` indica que todas las operaciones de la matriz se pueden controlar.</span><span class="sxs-lookup"><span data-stu-id="25e11-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="25e11-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="25e11-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="25e11-108">operaciones: ' t => de la [unidad](xref:microsoft.quantum.lang-ref.unit) CTL []</span><span class="sxs-lookup"><span data-stu-id="25e11-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="25e11-109">Secuencia de operaciones que se va a realizar en una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="25e11-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="25e11-110">Salida: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25e11-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="25e11-111">Nueva operación que realiza cada operación dada en secuencia en su entrada.</span><span class="sxs-lookup"><span data-stu-id="25e11-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="25e11-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="25e11-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="25e11-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="25e11-113">'T</span></span>

<span data-ttu-id="25e11-114">Destino en el que actúa cada una de las operaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="25e11-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="25e11-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25e11-115">See Also</span></span>

- [<span data-ttu-id="25e11-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="25e11-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)