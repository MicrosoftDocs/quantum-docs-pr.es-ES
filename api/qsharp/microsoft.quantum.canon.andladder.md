---
uid: Microsoft.Quantum.Canon.AndLadder
title: Operación AndLadder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729757"
---
# <a name="andladder-operation"></a><span data-ttu-id="e3863-102">Operación AndLadder</span><span class="sxs-lookup"><span data-stu-id="e3863-102">AndLadder operation</span></span>

<span data-ttu-id="e3863-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e3863-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e3863-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3863-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3863-105">Realiza una "y escalera" controlada en un registro de qubits de destino.</span><span class="sxs-lookup"><span data-stu-id="e3863-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e3863-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3863-106">Description</span></span>

<span data-ttu-id="e3863-107">Esta operación aplica una transformación descrita por la siguiente asignación de la base de cálculo: $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ Where $ \ket{x \_ 1, \dots, x \_ n} $ hace referencia a los Estados de base de cálculo de `controls` , y donde $ \ket{y \_ 1, \dots, y \_ {n-1}} $ hace referencia a los Estados de base de cálculo de `targets` .</span><span class="sxs-lookup"><span data-stu-id="e3863-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="e3863-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e3863-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="e3863-109">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="e3863-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="e3863-110">La puerta CCNOT que se va a usar para la construcción.</span><span class="sxs-lookup"><span data-stu-id="e3863-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="e3863-111">controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e3863-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e3863-112">Registro de qubits que se va a usar como control para la escalera y.</span><span class="sxs-lookup"><span data-stu-id="e3863-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="e3863-113">Esta operación deja Estados de base de cálculo `controls` invariable.</span><span class="sxs-lookup"><span data-stu-id="e3863-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="e3863-114">La longitud de `controls` debe ser al menos 2 y debe ser igual a uno más la longitud de `targets` .</span><span class="sxs-lookup"><span data-stu-id="e3863-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="e3863-115">destinos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e3863-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e3863-116">La longitud de `targets` debe ser al menos 1 y igual a la longitud de `controls` menos uno.</span><span class="sxs-lookup"><span data-stu-id="e3863-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3863-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3863-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e3863-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e3863-118">Remarks</span></span>

- <span data-ttu-id="e3863-119">Se utiliza como parte de <xref:microsoft.quantum.canon.applymulticontrolledc> y <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="e3863-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="e3863-120">En el diagrama de explicación y circuito, consulte la figura 4,10, sección 4,3 de Nielsen & Chuang.</span><span class="sxs-lookup"><span data-stu-id="e3863-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="e3863-121">Referencias</span><span class="sxs-lookup"><span data-stu-id="e3863-121">References</span></span>

- [<span data-ttu-id="e3863-122">*Michael A. Nielsen, Isaac L. Chuang* , cálculo de Quantum e información de Quantum</span><span class="sxs-lookup"><span data-stu-id="e3863-122"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)