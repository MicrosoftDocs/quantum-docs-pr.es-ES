---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: Operación ApplyOpRepeatedlyOverA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 30e91d8a0292c7389ad83f14e1b7d4a8248cbb96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841619"
---
# <a name="applyoprepeatedlyovera-operation"></a><span data-ttu-id="5bf4a-102">Operación ApplyOpRepeatedlyOverA</span><span class="sxs-lookup"><span data-stu-id="5bf4a-102">ApplyOpRepeatedlyOverA operation</span></span>

<span data-ttu-id="5bf4a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5bf4a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5bf4a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5bf4a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5bf4a-105">Aplica la misma operación sobre un registro de qubit varias veces.</span><span class="sxs-lookup"><span data-stu-id="5bf4a-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5bf4a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5bf4a-106">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="5bf4a-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="5bf4a-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="5bf4a-108">Operación que se va a aplicar varias veces en el registro qubit</span><span class="sxs-lookup"><span data-stu-id="5bf4a-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="5bf4a-109">destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="5bf4a-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="5bf4a-110">Matrices anidadas que describen los destinos de la operación.</span><span class="sxs-lookup"><span data-stu-id="5bf4a-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="5bf4a-111">Cada matriz debe contener una lista de ints que describe el qubits que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="5bf4a-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="5bf4a-112">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5bf4a-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5bf4a-113">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="5bf4a-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5bf4a-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5bf4a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5bf4a-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5bf4a-115">See Also</span></span>

- [<span data-ttu-id="5bf4a-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="5bf4a-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)