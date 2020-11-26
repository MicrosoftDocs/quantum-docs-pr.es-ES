---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Operación PrepareQubit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 84674d70d6a038ceaf1c637b22afa1b724d90795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193529"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="9f25d-102">Operación PrepareQubit</span><span class="sxs-lookup"><span data-stu-id="9f25d-102">PrepareQubit operation</span></span>

<span data-ttu-id="9f25d-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9f25d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9f25d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f25d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="9f25d-105">PrepareQubit está en desuso.</span><span class="sxs-lookup"><span data-stu-id="9f25d-105">PrepareQubit has been deprecated.</span></span> <span data-ttu-id="9f25d-106">Use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9f25d-106">Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.</span></span>

<span data-ttu-id="9f25d-107">Prepara un qubit en el eigenstate + 1 ( `Zero` ) del operador Pauli especificado.</span><span class="sxs-lookup"><span data-stu-id="9f25d-107">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="9f25d-108">Si se proporciona el operador de identidad, el qubit se prepara en el estado de mezcla máxima.</span><span class="sxs-lookup"><span data-stu-id="9f25d-108">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="9f25d-109">Si el qubit estaba inicialmente en el estado $ \ket {0} $, esta operación prepara el qubit en el eigenstate $ + $1 de un operador Pauli determinado, o bien, para `PauliI` , en el estado de mezcla máxima en su lugar (vea <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="9f25d-109">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="9f25d-110">Si el qubit estaba en un Estado distinto de $ \ket {0} $, esta operación aplica las siguientes puertas: $H $ para `PauliX` , $HS $ para `PauliY` , $I $ para `PauliZ` y <xref:microsoft.quantum.preparation.preparesinglequbitidentity> para `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="9f25d-110">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9f25d-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="9f25d-111">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="9f25d-112">base: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9f25d-112">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9f25d-113">Un operador Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="9f25d-113">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="9f25d-114">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9f25d-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9f25d-115">Qubit que se va a preparar.</span><span class="sxs-lookup"><span data-stu-id="9f25d-115">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f25d-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f25d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

