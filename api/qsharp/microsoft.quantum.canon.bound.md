---
uid: Microsoft.Quantum.Canon.Bound
title: Función enlazada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841063"
---
# <a name="bound-function"></a><span data-ttu-id="fbb2d-102">Función enlazada</span><span class="sxs-lookup"><span data-stu-id="fbb2d-102">Bound function</span></span>

<span data-ttu-id="fbb2d-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fbb2d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fbb2d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fbb2d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fbb2d-105">Dada una matriz de operaciones que actúan en una sola entrada, genera una nueva operación que realiza cada operación dada en secuencia.</span><span class="sxs-lookup"><span data-stu-id="fbb2d-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="fbb2d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="fbb2d-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="fbb2d-107">operaciones: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="fbb2d-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="fbb2d-108">Secuencia de operaciones que se va a realizar en una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="fbb2d-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="fbb2d-109">Salida: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="fbb2d-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fbb2d-110">Nueva operación que realiza cada operación dada en secuencia en su entrada.</span><span class="sxs-lookup"><span data-stu-id="fbb2d-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fbb2d-111">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="fbb2d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fbb2d-112">Traslada</span><span class="sxs-lookup"><span data-stu-id="fbb2d-112">'T</span></span>

<span data-ttu-id="fbb2d-113">Destino en el que actúa cada una de las operaciones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="fbb2d-113">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="fbb2d-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fbb2d-114">Example</span></span>

<span data-ttu-id="fbb2d-115">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="fbb2d-115">The following are equivalent:</span></span>

```qsharp
let bound = Bound([U, V]);
bound(x);
```

<span data-ttu-id="fbb2d-116">y</span><span class="sxs-lookup"><span data-stu-id="fbb2d-116">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="fbb2d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbb2d-117">See Also</span></span>

- [<span data-ttu-id="fbb2d-118">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="fbb2d-118">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="fbb2d-119">Microsoft. Quantum. Canon. Bounda</span><span class="sxs-lookup"><span data-stu-id="fbb2d-119">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="fbb2d-120">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="fbb2d-120">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)