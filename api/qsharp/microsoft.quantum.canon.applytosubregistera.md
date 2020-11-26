---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterA
title: Operación ApplyToSubregisterA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: edea0e565984cffb13b146cb336f90762f647636
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208064"
---
# <a name="applytosubregistera-operation"></a><span data-ttu-id="a04c2-102">Operación ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="a04c2-102">ApplyToSubregisterA operation</span></span>

<span data-ttu-id="a04c2-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a04c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a04c2-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a04c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a04c2-105">Aplica una operación a un subregistro de un registro, con qubits especificado por una matriz de sus índices.</span><span class="sxs-lookup"><span data-stu-id="a04c2-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="a04c2-106">El modificador `A` indica que la operación es adjointable.</span><span class="sxs-lookup"><span data-stu-id="a04c2-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[], target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a04c2-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="a04c2-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="a04c2-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="a04c2-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a04c2-109">Operación que se va a aplicar al subregistro.</span><span class="sxs-lookup"><span data-stu-id="a04c2-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="a04c2-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a04c2-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a04c2-111">Matriz de índices, que indica a qué qubits se aplicará la operación.</span><span class="sxs-lookup"><span data-stu-id="a04c2-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a04c2-112">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a04c2-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a04c2-113">Registro en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="a04c2-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a04c2-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a04c2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a04c2-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a04c2-115">See Also</span></span>

- [<span data-ttu-id="a04c2-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="a04c2-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)