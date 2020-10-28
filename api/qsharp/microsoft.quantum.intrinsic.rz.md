---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Operación RZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731348"
---
# <a name="rz-operation"></a><span data-ttu-id="2e3be-102">Operación RZ</span><span class="sxs-lookup"><span data-stu-id="2e3be-102">Rz operation</span></span>

<span data-ttu-id="2e3be-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2e3be-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2e3be-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e3be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e3be-105">Aplica un giro sobre el $z $ axis en un ángulo determinado.</span><span class="sxs-lookup"><span data-stu-id="2e3be-105">Applies a rotation about the $z$-axis by a given angle.</span></span>

<span data-ttu-id="2e3be-106">\begin{align} R_z (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \theta/2} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2e3be-106">\begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}.</span></span>
<span data-ttu-id="2e3be-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2e3be-107">\end{align}</span></span>

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="2e3be-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2e3be-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="2e3be-109">Theta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2e3be-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2e3be-110">Ángulo sobre el que se va a girar el qubit.</span><span class="sxs-lookup"><span data-stu-id="2e3be-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="2e3be-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2e3be-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2e3be-112">Qubit al que debe aplicarse la puerta.</span><span class="sxs-lookup"><span data-stu-id="2e3be-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e3be-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e3be-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2e3be-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2e3be-114">Remarks</span></span>

<span data-ttu-id="2e3be-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="2e3be-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
```