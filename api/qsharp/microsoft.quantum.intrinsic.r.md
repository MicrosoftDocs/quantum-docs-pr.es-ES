---
uid: Microsoft.Quantum.Intrinsic.R
title: Operación de R
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 1df4b1197e885e479339e542e8c1ffaeb392543d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818717"
---
# <a name="r-operation"></a><span data-ttu-id="da2a4-102">Operación de R</span><span class="sxs-lookup"><span data-stu-id="da2a4-102">R operation</span></span>

<span data-ttu-id="da2a4-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="da2a4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="da2a4-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="da2a4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="da2a4-105">Aplica un giro sobre el eje Pauli especificado.</span><span class="sxs-lookup"><span data-stu-id="da2a4-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="da2a4-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_ {\mu}/2}, \end{align} donde $ \mu \en \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="da2a4-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="da2a4-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="da2a4-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="da2a4-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="da2a4-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="da2a4-109">Operador Pauli ($ \mu $) que se va un exponente para formar el giro.</span><span class="sxs-lookup"><span data-stu-id="da2a4-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="da2a4-110">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="da2a4-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="da2a4-111">Ángulo sobre el que se va a girar el qubit.</span><span class="sxs-lookup"><span data-stu-id="da2a4-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="da2a4-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="da2a4-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="da2a4-113">Qubit al que debe aplicarse la puerta.</span><span class="sxs-lookup"><span data-stu-id="da2a4-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da2a4-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da2a4-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="da2a4-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="da2a4-115">Remarks</span></span>

<span data-ttu-id="da2a4-116">Cuando se llama con `pauli = PauliI` , esta operación aplica una *fase global*.</span><span class="sxs-lookup"><span data-stu-id="da2a4-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="da2a4-117">Esta fase puede ser significativa cuando se usa con el `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="da2a4-117">This phase can be significant when used with the `Controlled` functor.</span></span>