---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2ca32cf8c85f33f498a30f71833b3dd69db6da6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728420"
---
# <a name="restrictedtosubregisterc-function"></a><span data-ttu-id="594ea-102">RestrictedToSubregisterC función)</span><span class="sxs-lookup"><span data-stu-id="594ea-102">RestrictedToSubregisterC function</span></span>

<span data-ttu-id="594ea-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="594ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="594ea-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="594ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="594ea-105">Restringe una operación a una matriz de índices de un registro, es decir, un subregistro.</span><span class="sxs-lookup"><span data-stu-id="594ea-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="594ea-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="594ea-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="594ea-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="594ea-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="594ea-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="594ea-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="594ea-109">Operación que se va a restringir a un subregistro.</span><span class="sxs-lookup"><span data-stu-id="594ea-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="594ea-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="594ea-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="594ea-111">Matriz de índices, que indica a qué qubits se restringe la operación.</span><span class="sxs-lookup"><span data-stu-id="594ea-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit-ctl"></a><span data-ttu-id="594ea-112">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="594ea-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="594ea-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="594ea-113">See Also</span></span>

- [<span data-ttu-id="594ea-114">Microsoft. Quantum. Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="594ea-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)