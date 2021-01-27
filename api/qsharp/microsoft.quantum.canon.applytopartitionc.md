---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: Operación ApplyToPartitionC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 43cf43fa2bf9c00a4096b39555b8f6080dd506d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850525"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="d2a5a-102">Operación ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="d2a5a-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="d2a5a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d2a5a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d2a5a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2a5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2a5a-105">Aplica un par de operaciones a una partición determinada de un registro en dos partes.</span><span class="sxs-lookup"><span data-stu-id="d2a5a-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="d2a5a-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="d2a5a-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="d2a5a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d2a5a-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="d2a5a-108">OP: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="d2a5a-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d2a5a-109">Par de operaciones que se van a aplicar a la partición especificada.</span><span class="sxs-lookup"><span data-stu-id="d2a5a-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="d2a5a-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2a5a-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2a5a-111">Número de qubits del destino que se van a colocar en la primera parte de la partición.</span><span class="sxs-lookup"><span data-stu-id="d2a5a-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="d2a5a-112">El Qubits restante constituye la segunda parte de la partición.</span><span class="sxs-lookup"><span data-stu-id="d2a5a-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d2a5a-113">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d2a5a-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d2a5a-114">Registro de qubits que se va a particionar y en el que se va a realizar la operación con las dos operaciones dadas.</span><span class="sxs-lookup"><span data-stu-id="d2a5a-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d2a5a-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2a5a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d2a5a-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2a5a-116">See Also</span></span>

- [<span data-ttu-id="d2a5a-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="d2a5a-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)