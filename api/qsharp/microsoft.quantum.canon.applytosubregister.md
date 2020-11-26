---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: Operación ApplyToSubregister
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: d4589edaadf59bbfff432bf49be2ce14fcff6ed1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208115"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="ef8d3-102">Operación ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="ef8d3-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="ef8d3-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef8d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef8d3-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef8d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef8d3-105">Aplica una operación a un subregistro de un registro, con qubits especificado por una matriz de sus índices.</span><span class="sxs-lookup"><span data-stu-id="ef8d3-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ef8d3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ef8d3-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="ef8d3-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ef8d3-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ef8d3-108">Operación que se va a aplicar al subregistro.</span><span class="sxs-lookup"><span data-stu-id="ef8d3-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="ef8d3-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ef8d3-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ef8d3-110">Matriz de índices, que indica a qué qubits se aplicará la operación.</span><span class="sxs-lookup"><span data-stu-id="ef8d3-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ef8d3-111">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ef8d3-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ef8d3-112">Registro en el que actúa la operación.</span><span class="sxs-lookup"><span data-stu-id="ef8d3-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ef8d3-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef8d3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ef8d3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef8d3-114">See Also</span></span>

- [<span data-ttu-id="ef8d3-115">Microsoft. Quantum. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="ef8d3-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="ef8d3-116">Microsoft. Quantum. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="ef8d3-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="ef8d3-117">Microsoft. Quantum. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="ef8d3-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)