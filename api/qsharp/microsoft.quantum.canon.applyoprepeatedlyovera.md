---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverA
title: Operación ApplyOpRepeatedlyOverA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverA
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 2e8ef7e943cfd2c0634f16566a018f386aad659f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729417"
---
# <a name="applyoprepeatedlyovera-operation"></a><span data-ttu-id="b2f62-102">Operación ApplyOpRepeatedlyOverA</span><span class="sxs-lookup"><span data-stu-id="b2f62-102">ApplyOpRepeatedlyOverA operation</span></span>

<span data-ttu-id="b2f62-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b2f62-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b2f62-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2f62-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2f62-105">Aplica la misma operación sobre un registro de qubit varias veces.</span><span class="sxs-lookup"><span data-stu-id="b2f62-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverA (op : (Qubit[] => Unit is Adj), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b2f62-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b2f62-106">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="b2f62-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2f62-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="b2f62-108">Operación que se va a aplicar varias veces en el registro qubit</span><span class="sxs-lookup"><span data-stu-id="b2f62-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="b2f62-109">destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="b2f62-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="b2f62-110">Matrices anidadas que describen los destinos de la operación.</span><span class="sxs-lookup"><span data-stu-id="b2f62-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="b2f62-111">Cada matriz debe contener una lista de ints que describe el qubits que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="b2f62-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="b2f62-112">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2f62-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2f62-113">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="b2f62-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2f62-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2f62-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="b2f62-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2f62-115">See Also</span></span>

- [<span data-ttu-id="b2f62-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="b2f62-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)