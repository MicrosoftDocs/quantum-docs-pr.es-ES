---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: Operación RFrac
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: c80bb2b394e83c1133ed6ddc1640a3d88563ca6e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818482"
---
# <a name="rfrac-operation"></a><span data-ttu-id="78d08-102">Operación RFrac</span><span class="sxs-lookup"><span data-stu-id="78d08-102">RFrac operation</span></span>

<span data-ttu-id="78d08-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="78d08-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="78d08-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="78d08-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="78d08-105">Aplica un giro sobre el eje Pauli determinado mediante un ángulo especificado como fracción Dyadic.</span><span class="sxs-lookup"><span data-stu-id="78d08-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="78d08-106">\begin{align} R_ {\mu} (n, k) \mathrel{: =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}, \end{align} donde $ \mu \en \{ i, X, y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="78d08-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="78d08-107">Esta operación utiliza la Convención de signo **opuesto** de @"microsoft.quantum.intrinsic.r" .</span><span class="sxs-lookup"><span data-stu-id="78d08-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="78d08-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="78d08-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="78d08-109">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="78d08-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="78d08-110">Operador Pauli que se va un exponente para formar el giro.</span><span class="sxs-lookup"><span data-stu-id="78d08-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="78d08-111">Numerador: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="78d08-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="78d08-112">Numerador en la representación de fracción de Dyadic del ángulo por el que se va a girar el qubit.</span><span class="sxs-lookup"><span data-stu-id="78d08-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="78d08-113">potencia: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="78d08-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="78d08-114">Potencia de dos que especifica el denominador del ángulo por el que se va a girar el qubit.</span><span class="sxs-lookup"><span data-stu-id="78d08-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="78d08-115">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="78d08-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="78d08-116">Qubit al que debe aplicarse la puerta.</span><span class="sxs-lookup"><span data-stu-id="78d08-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78d08-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78d08-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="78d08-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="78d08-118">Remarks</span></span>

<span data-ttu-id="78d08-119">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="78d08-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```