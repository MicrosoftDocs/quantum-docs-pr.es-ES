---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: Operación ApplyToPartitionCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 572cf824647b3e7f7c0e17c797d519f41914f79d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841278"
---
# <a name="applytopartitionca-operation"></a><span data-ttu-id="60b49-102">Operación ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="60b49-102">ApplyToPartitionCA operation</span></span>

<span data-ttu-id="60b49-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="60b49-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="60b49-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60b49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60b49-105">Aplica un par de operaciones a una partición determinada de un registro en dos partes.</span><span class="sxs-lookup"><span data-stu-id="60b49-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="60b49-106">El modificador `CA` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="60b49-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="60b49-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="60b49-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="60b49-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="60b49-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="60b49-109">Par de operaciones que se van a aplicar a la partición especificada.</span><span class="sxs-lookup"><span data-stu-id="60b49-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="60b49-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="60b49-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="60b49-111">Número de qubits del destino que se van a colocar en la primera parte de la partición.</span><span class="sxs-lookup"><span data-stu-id="60b49-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="60b49-112">El Qubits restante constituye la segunda parte de la partición.</span><span class="sxs-lookup"><span data-stu-id="60b49-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="60b49-113">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="60b49-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="60b49-114">Registro de qubits que se va a particionar y en el que se va a realizar la operación con las dos operaciones dadas.</span><span class="sxs-lookup"><span data-stu-id="60b49-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60b49-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60b49-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="60b49-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60b49-116">See Also</span></span>

- [<span data-ttu-id="60b49-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="60b49-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)