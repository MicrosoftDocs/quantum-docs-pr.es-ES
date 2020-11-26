---
uid: Microsoft.Quantum.Intrinsic.T
title: Operación T
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 352ef2c1b15a46dea85c420fc6f1cfab0382e73a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198408"
---
# <a name="t-operation"></a><span data-ttu-id="2d171-102">Operación T</span><span class="sxs-lookup"><span data-stu-id="2d171-102">T operation</span></span>

<span data-ttu-id="2d171-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2d171-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2d171-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2d171-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2d171-105">Aplica la puerta T a un único qubit.</span><span class="sxs-lookup"><span data-stu-id="2d171-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2d171-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d171-106">Description</span></span>

<span data-ttu-id="2d171-107">Esta operación la puede simular la matriz de unitarios \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2d171-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="2d171-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2d171-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="2d171-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="2d171-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="2d171-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2d171-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2d171-111">Qubit al que debe aplicarse la puerta.</span><span class="sxs-lookup"><span data-stu-id="2d171-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d171-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d171-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

