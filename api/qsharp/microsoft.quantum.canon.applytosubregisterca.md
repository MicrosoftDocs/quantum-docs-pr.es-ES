---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: Operación ApplyToSubregisterCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: a5ebfb17b1e66bd509f3a562f852986c83d0fef0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208013"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="2140f-102">Operación ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="2140f-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="2140f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2140f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2140f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2140f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2140f-105">Aplica una operación a un subregistro de un registro, con qubits especificado por una matriz de sus índices.</span><span class="sxs-lookup"><span data-stu-id="2140f-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="2140f-106">El modificador `CA` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="2140f-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2140f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="2140f-107">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="2140f-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="2140f-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2140f-109">Operación que se va a aplicar al subregistro.</span><span class="sxs-lookup"><span data-stu-id="2140f-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="2140f-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2140f-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2140f-111">Matriz de índices, que indica a qué qubits se aplicará la operación.</span><span class="sxs-lookup"><span data-stu-id="2140f-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2140f-112">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2140f-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2140f-113">Registro en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="2140f-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2140f-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2140f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2140f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2140f-115">See Also</span></span>

- [<span data-ttu-id="2140f-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="2140f-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)