---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Operación Ry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 9966693eb7283e855f7b72e910aa3604d6c2bd61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730773"
---
# <a name="ry-operation"></a><span data-ttu-id="86b87-102">Operación Ry</span><span class="sxs-lookup"><span data-stu-id="86b87-102">Ry operation</span></span>

<span data-ttu-id="86b87-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="86b87-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="86b87-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="86b87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="86b87-105">Aplica un giro sobre el $y $ AXIS en un ángulo determinado.</span><span class="sxs-lookup"><span data-stu-id="86b87-105">Applies a rotation about the $y$-axis by a given angle.</span></span>

<span data-ttu-id="86b87-106">\begin{align} R_y (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_y/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-\sin \frac{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{bmatrix}.  </span><span class="sxs-lookup"><span data-stu-id="86b87-106">\begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}.</span></span>
<span data-ttu-id="86b87-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="86b87-107">\end{align}</span></span>

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="86b87-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="86b87-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="86b87-109">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="86b87-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="86b87-110">Ángulo sobre el que se va a girar el qubit.</span><span class="sxs-lookup"><span data-stu-id="86b87-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="86b87-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="86b87-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="86b87-112">Qubit al que debe aplicarse la puerta.</span><span class="sxs-lookup"><span data-stu-id="86b87-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86b87-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86b87-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="86b87-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86b87-114">Remarks</span></span>

<span data-ttu-id="86b87-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="86b87-115">Equivalent to:</span></span>

```qsharp
R(PauliY, theta, qubit);
```