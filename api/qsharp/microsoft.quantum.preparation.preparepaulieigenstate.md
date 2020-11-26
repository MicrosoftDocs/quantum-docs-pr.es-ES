---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Operación PreparePauliEigenstate
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193699"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="87877-102">Operación PreparePauliEigenstate</span><span class="sxs-lookup"><span data-stu-id="87877-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="87877-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="87877-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="87877-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87877-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87877-105">Prepara un qubit en el eigenstate positivo de un operador Pauli determinado.</span><span class="sxs-lookup"><span data-stu-id="87877-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="87877-106">Si se proporciona el operador de identidad, el qubit se prepara en el estado de mezcla máxima.</span><span class="sxs-lookup"><span data-stu-id="87877-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="87877-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="87877-107">Description</span></span>

<span data-ttu-id="87877-108">Si el qubit estaba inicialmente en el estado $ \ket {0} $, esta operación prepara el qubit en el eigenstate $ + $1 de un operador Pauli determinado, o bien, para `PauliI` , en el estado de mezcla máxima en su lugar (vea <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="87877-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="87877-109">Si el qubit estaba en un Estado distinto de $ \ket {0} $, esta operación aplica las siguientes puertas: $H $ para `PauliX` , $HS $ para `PauliY` , $I $ para `PauliZ` y <xref:microsoft.quantum.preparation.preparesinglequbitidentity> para `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="87877-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="87877-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="87877-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="87877-111">base: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="87877-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="87877-112">Un operador Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="87877-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="87877-113">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="87877-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="87877-114">Qubit que se va a preparar.</span><span class="sxs-lookup"><span data-stu-id="87877-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="87877-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87877-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

