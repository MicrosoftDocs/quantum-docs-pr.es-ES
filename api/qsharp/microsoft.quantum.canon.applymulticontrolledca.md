---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Operación ApplyMultiControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729470"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="cfb97-102">Operación ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="cfb97-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="cfb97-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cfb97-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cfb97-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cfb97-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cfb97-105">Aplica una versión con control de multiplicación de una operación controlada de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="cfb97-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="cfb97-106">El modificador `CA` indica que la operación de un solo qubit es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="cfb97-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cfb97-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cfb97-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit-adj"></a><span data-ttu-id="cfb97-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfb97-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="cfb97-109">Operación controlada en un único qubit.</span><span class="sxs-lookup"><span data-stu-id="cfb97-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="cfb97-110">Se supone que el primer qubit en el argumento de la operación es un control y se supone que el resto es qubits de destino.</span><span class="sxs-lookup"><span data-stu-id="cfb97-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="cfb97-111">`ApplyMultiControlled` siempre llama a `singlyControlledOp` con un argumento de longitud de al menos 1.</span><span class="sxs-lookup"><span data-stu-id="cfb97-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="cfb97-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="cfb97-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="cfb97-113">La puerta controlada por control controlada que se va a usar para la construcción.</span><span class="sxs-lookup"><span data-stu-id="cfb97-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="cfb97-114">controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cfb97-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cfb97-115">Qubits en el que `singlyControlledOp` se va a controlar.</span><span class="sxs-lookup"><span data-stu-id="cfb97-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="cfb97-116">La longitud de `controls` debe ser al menos 1.</span><span class="sxs-lookup"><span data-stu-id="cfb97-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="cfb97-117">destinos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cfb97-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cfb97-118">Qubits de destino que `singlyControlledOp` actúa sobre.</span><span class="sxs-lookup"><span data-stu-id="cfb97-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cfb97-119">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfb97-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cfb97-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cfb97-120">Remarks</span></span>

<span data-ttu-id="cfb97-121">Esta operación solo usa Clean ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="cfb97-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="cfb97-122">En el diagrama de explicación y circuito, vea la figura 4,10, sección 4,3 de Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="cfb97-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="cfb97-123">Referencias</span><span class="sxs-lookup"><span data-stu-id="cfb97-123">References</span></span>

- [<span data-ttu-id="cfb97-124">*Michael A. Nielsen, Isaac L. Chuang* , cálculo de Quantum e información de Quantum</span><span class="sxs-lookup"><span data-stu-id="cfb97-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="cfb97-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfb97-125">See Also</span></span>

- [<span data-ttu-id="cfb97-126">Microsoft. Quantum. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="cfb97-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)