---
uid: Microsoft.Quantum.Intrinsic.R1
title: Operación R1
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: a98c2cc0b309a239650afd2910cc74dffa9f899a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198816"
---
# <a name="r1-operation"></a><span data-ttu-id="2720c-102">Operación R1</span><span class="sxs-lookup"><span data-stu-id="2720c-102">R1 operation</span></span>

<span data-ttu-id="2720c-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2720c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2720c-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2720c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2720c-105">Aplica un giro sobre el estado de $ \ket {1} $ en un ángulo determinado.</span><span class="sxs-lookup"><span data-stu-id="2720c-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="2720c-106">\begin{align} R_1 (\theta) \mathrel{: =} \operatorname{DIAG} (1, e ^ {i\theta}).</span><span class="sxs-lookup"><span data-stu-id="2720c-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="2720c-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2720c-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2720c-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2720c-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="2720c-109">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2720c-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2720c-110">Ángulo sobre el que se va a girar el qubit.</span><span class="sxs-lookup"><span data-stu-id="2720c-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="2720c-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2720c-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2720c-112">Qubit al que debe aplicarse la puerta.</span><span class="sxs-lookup"><span data-stu-id="2720c-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2720c-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2720c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2720c-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2720c-114">Remarks</span></span>

<span data-ttu-id="2720c-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="2720c-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```