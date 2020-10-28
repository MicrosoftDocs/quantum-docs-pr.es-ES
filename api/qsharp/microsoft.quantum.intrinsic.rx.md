---
uid: Microsoft.Quantum.Intrinsic.Rx
title: Operación RX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 6d11c8fa3c3fb2c07a88fdf2cba0ff2a7f51bf6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732933"
---
# <a name="rx-operation"></a><span data-ttu-id="ccdf6-102">Operación RX</span><span class="sxs-lookup"><span data-stu-id="ccdf6-102">Rx operation</span></span>

<span data-ttu-id="ccdf6-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ccdf6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ccdf6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ccdf6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ccdf6-105">Aplica un giro sobre el $x $ AXIS en un ángulo determinado.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-105">Applies a rotation about the $x$-axis by a given angle.</span></span>

<span data-ttu-id="ccdf6-106">\begin{align} R_x (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-i\sin \frac{\theta} {2} \\ \\ -i\sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="ccdf6-106">\begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="ccdf6-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="ccdf6-107">\end{align}</span></span>

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ccdf6-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="ccdf6-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="ccdf6-109">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ccdf6-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ccdf6-110">Ángulo sobre el que se va a girar el qubit.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="ccdf6-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ccdf6-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ccdf6-112">Qubit al que debe aplicarse la puerta.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ccdf6-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ccdf6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ccdf6-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ccdf6-114">Remarks</span></span>

<span data-ttu-id="ccdf6-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="ccdf6-115">Equivalent to:</span></span>

```qsharp
R(PauliX, theta, qubit);
```