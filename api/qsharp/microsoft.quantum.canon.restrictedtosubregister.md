---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: RestrictedToSubregister función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a8b599035de6fede10bdaf8cef17f2124a59f064
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728432"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="39b8e-102">RestrictedToSubregister función)</span><span class="sxs-lookup"><span data-stu-id="39b8e-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="39b8e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39b8e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39b8e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39b8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39b8e-105">Restringe una operación a una matriz de índices de un registro, es decir, un subregistro.</span><span class="sxs-lookup"><span data-stu-id="39b8e-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="39b8e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="39b8e-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="39b8e-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="39b8e-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="39b8e-108">Operación que se va a restringir a un subregistro.</span><span class="sxs-lookup"><span data-stu-id="39b8e-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="39b8e-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="39b8e-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="39b8e-110">Matriz de índices, que indica a qué qubits se restringe la operación.</span><span class="sxs-lookup"><span data-stu-id="39b8e-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="39b8e-111">Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="39b8e-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="39b8e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39b8e-112">See Also</span></span>

- [<span data-ttu-id="39b8e-113">Microsoft. Quantum. Canon. RestrictedToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="39b8e-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="39b8e-114">Microsoft. Quantum. Canon. RestrictedToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="39b8e-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="39b8e-115">Microsoft. Quantum. Canon. RestrictedToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="39b8e-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)