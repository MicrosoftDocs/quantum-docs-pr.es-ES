---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: Operación RFrac
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732940"
---
# <a name="rfrac-operation"></a><span data-ttu-id="0a9bb-102">Operación RFrac</span><span class="sxs-lookup"><span data-stu-id="0a9bb-102">RFrac operation</span></span>

<span data-ttu-id="0a9bb-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0a9bb-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0a9bb-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0a9bb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0a9bb-105">Aplica un giro sobre el eje Pauli determinado mediante un ángulo especificado como fracción Dyadic.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="0a9bb-106">\begin{align} R_ {\mu} (n, k) \mathrel{: =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}, \end{align} donde $ \mu \en \{ i, X, y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="0a9bb-107">Esta operación utiliza la Convención de signo **opuesto** de @"microsoft.quantum.intrinsic.r" .</span><span class="sxs-lookup"><span data-stu-id="0a9bb-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="0a9bb-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="0a9bb-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="0a9bb-109">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="0a9bb-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="0a9bb-110">Operador Pauli que se va un exponente para formar el giro.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="0a9bb-111">Numerador: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a9bb-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0a9bb-112">Numerador en la representación de fracción de Dyadic del ángulo por el que se va a girar el qubit.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="0a9bb-113">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a9bb-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0a9bb-114">Potencia de dos que especifica el denominador del ángulo por el que se va a girar el qubit.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="0a9bb-115">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0a9bb-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0a9bb-116">Qubit al que debe aplicarse la puerta.</span><span class="sxs-lookup"><span data-stu-id="0a9bb-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a9bb-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a9bb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0a9bb-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0a9bb-118">Remarks</span></span>

<span data-ttu-id="0a9bb-119">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="0a9bb-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```