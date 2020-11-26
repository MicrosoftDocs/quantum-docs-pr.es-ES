---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: Operación ApplyToPartition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: f36bccb727bb38a0cdf4f1fedabc9f3f554059ab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208404"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="96589-102">Operación ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="96589-102">ApplyToPartition operation</span></span>

<span data-ttu-id="96589-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="96589-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="96589-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="96589-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="96589-105">Aplica un par de operaciones a una partición determinada de un registro en dos partes.</span><span class="sxs-lookup"><span data-stu-id="96589-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="96589-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="96589-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="96589-107">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="96589-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="96589-108">Par de operaciones que se van a aplicar a la partición especificada.</span><span class="sxs-lookup"><span data-stu-id="96589-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="96589-109">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="96589-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="96589-110">Número de qubits del destino que se van a colocar en la primera parte de la partición.</span><span class="sxs-lookup"><span data-stu-id="96589-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="96589-111">El Qubits restante constituye la segunda parte de la partición.</span><span class="sxs-lookup"><span data-stu-id="96589-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="96589-112">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="96589-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="96589-113">Registro de qubits que se va a particionar y en el que se va a realizar la operación con las dos operaciones dadas.</span><span class="sxs-lookup"><span data-stu-id="96589-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="96589-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96589-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="96589-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96589-115">See Also</span></span>

- [<span data-ttu-id="96589-116">Microsoft. Quantum. Canon. ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="96589-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="96589-117">Microsoft. Quantum. Canon. ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="96589-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="96589-118">Microsoft. Quantum. Canon. ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="96589-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)