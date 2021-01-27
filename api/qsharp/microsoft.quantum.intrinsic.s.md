---
uid: Microsoft.Quantum.Intrinsic.S
title: Operación S
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: be9078dfdcc4eecf317b0542b1c42a8d60466a5f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817532"
---
# <a name="s-operation"></a><span data-ttu-id="346dd-102">Operación S</span><span class="sxs-lookup"><span data-stu-id="346dd-102">S operation</span></span>

<span data-ttu-id="346dd-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="346dd-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="346dd-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="346dd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="346dd-105">Aplica la puerta S a un único qubit.</span><span class="sxs-lookup"><span data-stu-id="346dd-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="346dd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="346dd-106">Description</span></span>

<span data-ttu-id="346dd-107">Esta operación la puede simular la matriz de unitarios \begin{align} S \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="346dd-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="346dd-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="346dd-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="346dd-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="346dd-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="346dd-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="346dd-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="346dd-111">Qubit al que debe aplicarse la puerta.</span><span class="sxs-lookup"><span data-stu-id="346dd-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="346dd-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="346dd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

