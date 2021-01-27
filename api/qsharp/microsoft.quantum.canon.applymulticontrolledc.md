---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: Operación ApplyMultiControlledC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: bf6b78cd18a827a9a4fd9d61dfd4d240de3503e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844864"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="7f5db-102">Operación ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="7f5db-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="7f5db-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7f5db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7f5db-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7f5db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7f5db-105">Aplica una versión con control de multiplicación de una operación controlada de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="7f5db-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="7f5db-106">El modificador `C` indica que la operación de un solo qubit es controlable.</span><span class="sxs-lookup"><span data-stu-id="7f5db-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7f5db-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="7f5db-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="7f5db-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7f5db-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7f5db-109">Operación controlada en un único qubit.</span><span class="sxs-lookup"><span data-stu-id="7f5db-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="7f5db-110">Se supone que el primer qubit en el argumento de la operación es un control y se supone que el resto es qubits de destino.</span><span class="sxs-lookup"><span data-stu-id="7f5db-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="7f5db-111">`ApplyMultiControlled` siempre llama a `singlyControlledOp` con un argumento de longitud de al menos 1.</span><span class="sxs-lookup"><span data-stu-id="7f5db-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="7f5db-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="7f5db-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="7f5db-113">La puerta controlada por control controlada que se va a usar para la construcción.</span><span class="sxs-lookup"><span data-stu-id="7f5db-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="7f5db-114">controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7f5db-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7f5db-115">Qubits en el que `singlyControlledOp` se va a controlar.</span><span class="sxs-lookup"><span data-stu-id="7f5db-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="7f5db-116">La longitud de `controls` debe ser al menos 1.</span><span class="sxs-lookup"><span data-stu-id="7f5db-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="7f5db-117">destinos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7f5db-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7f5db-118">Qubits de destino que `singlyControlledOp` actúa sobre.</span><span class="sxs-lookup"><span data-stu-id="7f5db-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f5db-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f5db-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7f5db-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7f5db-120">Remarks</span></span>

<span data-ttu-id="7f5db-121">Esta operación solo usa Clean ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="7f5db-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="7f5db-122">En el diagrama de explicación y circuito, vea la figura 4,10, sección 4,3 de Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="7f5db-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="7f5db-123">Referencias</span><span class="sxs-lookup"><span data-stu-id="7f5db-123">References</span></span>

- [<span data-ttu-id="7f5db-124">*Michael A. Nielsen, Isaac L. Chuang*, cálculo de Quantum e información de Quantum</span><span class="sxs-lookup"><span data-stu-id="7f5db-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="7f5db-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f5db-125">See Also</span></span>

- [<span data-ttu-id="7f5db-126">Microsoft. Quantum. Canon. ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="7f5db-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)