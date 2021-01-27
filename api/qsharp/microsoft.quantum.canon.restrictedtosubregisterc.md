---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: RestrictedToSubregisterC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: f44e9ea4d17dcadc6d3c64941529db819b7f9784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840214"
---
# <a name="restrictedtosubregisterc-function"></a><span data-ttu-id="2e2ff-102">RestrictedToSubregisterC función)</span><span class="sxs-lookup"><span data-stu-id="2e2ff-102">RestrictedToSubregisterC function</span></span>

<span data-ttu-id="2e2ff-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2e2ff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2e2ff-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e2ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e2ff-105">Restringe una operación a una matriz de índices de un registro, es decir, un subregistro.</span><span class="sxs-lookup"><span data-stu-id="2e2ff-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="2e2ff-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="2e2ff-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="2e2ff-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="2e2ff-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="2e2ff-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="2e2ff-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2e2ff-109">Operación que se va a restringir a un subregistro.</span><span class="sxs-lookup"><span data-stu-id="2e2ff-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="2e2ff-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2e2ff-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2e2ff-111">Matriz de índices, que indica a qué qubits se restringe la operación.</span><span class="sxs-lookup"><span data-stu-id="2e2ff-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit--is-ctl"></a><span data-ttu-id="2e2ff-112">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="2e2ff-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="2e2ff-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e2ff-113">See Also</span></span>

- [<span data-ttu-id="2e2ff-114">Microsoft. Quantum. Canon. RestrictedToSubregister</span><span class="sxs-lookup"><span data-stu-id="2e2ff-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)