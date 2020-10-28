---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: Operación CNOT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732460"
---
# <a name="cnot-operation"></a><span data-ttu-id="b9610-102">Operación CNOT</span><span class="sxs-lookup"><span data-stu-id="b9610-102">CNOT operation</span></span>

<span data-ttu-id="b9610-103">Espacio de nombres: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="b9610-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="b9610-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b9610-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b9610-105">Aplica la puerta controlada-NOT (CNOT) a un par de qubits.</span><span class="sxs-lookup"><span data-stu-id="b9610-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="b9610-106">\begin{align} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 \\ \\ & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="b9610-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="b9610-107">donde se ordenan las filas y las columnas como en la guía de conceptos de Quantum.</span><span class="sxs-lookup"><span data-stu-id="b9610-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b9610-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b9610-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="b9610-109">control: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b9610-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b9610-110">Controle qubit para la puerta CNOT.</span><span class="sxs-lookup"><span data-stu-id="b9610-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b9610-111">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b9610-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b9610-112">Qubit de destino para la puerta CNOT.</span><span class="sxs-lookup"><span data-stu-id="b9610-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b9610-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b9610-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b9610-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b9610-114">Remarks</span></span>

<span data-ttu-id="b9610-115">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="b9610-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```