---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOverC
title: Operación ApplyOpRepeatedlyOverC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOverC
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: effd61e6c012dcf81a83383c3fd43cf745d18117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729411"
---
# <a name="applyoprepeatedlyoverc-operation"></a><span data-ttu-id="284f1-102">Operación ApplyOpRepeatedlyOverC</span><span class="sxs-lookup"><span data-stu-id="284f1-102">ApplyOpRepeatedlyOverC operation</span></span>

<span data-ttu-id="284f1-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="284f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="284f1-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="284f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="284f1-105">Aplica la misma operación sobre un registro de qubit varias veces.</span><span class="sxs-lookup"><span data-stu-id="284f1-105">Applies the same op over a qubit register multiple times.</span></span>

```qsharp
operation ApplyOpRepeatedlyOverC (op : (Qubit[] => Unit is Ctl), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="284f1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="284f1-106">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="284f1-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="284f1-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="284f1-108">Operación que se va a aplicar varias veces en el registro qubit</span><span class="sxs-lookup"><span data-stu-id="284f1-108">An operation to be applied multiple times on the qubit register</span></span>


### <a name="targets--int"></a><span data-ttu-id="284f1-109">destinos: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="284f1-109">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="284f1-110">Matrices anidadas que describen los destinos de la operación.</span><span class="sxs-lookup"><span data-stu-id="284f1-110">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="284f1-111">Cada matriz debe contener una lista de ints que describe el qubits que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="284f1-111">Each array should contain a list of ints describing the qubits to be used.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="284f1-112">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="284f1-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="284f1-113">Registro de qubit en el que se va a actuar.</span><span class="sxs-lookup"><span data-stu-id="284f1-113">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="284f1-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="284f1-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="284f1-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="284f1-115">See Also</span></span>

- [<span data-ttu-id="284f1-116">Microsoft. Quantum. Canon. ApplySeriesOfOps</span><span class="sxs-lookup"><span data-stu-id="284f1-116">Microsoft.Quantum.Canon.ApplySeriesOfOps</span></span>](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)