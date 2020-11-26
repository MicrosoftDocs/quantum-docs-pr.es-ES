---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: Operación ApplyToPartitionA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 79f8fbed1592670031b3348155cdd4000eadc1fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208353"
---
# <a name="applytopartitiona-operation"></a><span data-ttu-id="aa582-102">Operación ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="aa582-102">ApplyToPartitionA operation</span></span>

<span data-ttu-id="aa582-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa582-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa582-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa582-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa582-105">Aplica un par de operaciones a una partición determinada de un registro en dos partes.</span><span class="sxs-lookup"><span data-stu-id="aa582-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="aa582-106">El modificador `A` indica que la operación es adjointable.</span><span class="sxs-lookup"><span data-stu-id="aa582-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="aa582-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="aa582-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="aa582-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="aa582-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="aa582-109">Par de operaciones que se van a aplicar a la partición especificada.</span><span class="sxs-lookup"><span data-stu-id="aa582-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="aa582-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aa582-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aa582-111">Número de qubits del destino que se van a colocar en la primera parte de la partición.</span><span class="sxs-lookup"><span data-stu-id="aa582-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="aa582-112">El Qubits restante constituye la segunda parte de la partición.</span><span class="sxs-lookup"><span data-stu-id="aa582-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="aa582-113">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aa582-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aa582-114">Registro de qubits que se va a particionar y en el que se va a realizar la operación con las dos operaciones dadas.</span><span class="sxs-lookup"><span data-stu-id="aa582-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa582-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa582-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="aa582-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa582-116">See Also</span></span>

- [<span data-ttu-id="aa582-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="aa582-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)