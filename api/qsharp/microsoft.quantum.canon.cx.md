---
uid: Microsoft.Quantum.Canon.CX
title: Operación de CX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728787"
---
# <a name="cx-operation"></a><span data-ttu-id="bd688-102">Operación de CX</span><span class="sxs-lookup"><span data-stu-id="bd688-102">CX operation</span></span>

<span data-ttu-id="bd688-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd688-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd688-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd688-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd688-105">Aplica la puerta controlada X (CX) a un par de qubits.</span><span class="sxs-lookup"><span data-stu-id="bd688-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="bd688-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, donde las filas y columnas están organizadas como en la guía de conceptos de Quantum.</span><span class="sxs-lookup"><span data-stu-id="bd688-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="bd688-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="bd688-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="bd688-108">control: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bd688-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bd688-109">Controle qubit para la puerta CX.</span><span class="sxs-lookup"><span data-stu-id="bd688-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="bd688-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bd688-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bd688-111">Destino qubit para la puerta CX.</span><span class="sxs-lookup"><span data-stu-id="bd688-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd688-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd688-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bd688-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bd688-113">Remarks</span></span>

<span data-ttu-id="bd688-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="bd688-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="bd688-115">y para:</span><span class="sxs-lookup"><span data-stu-id="bd688-115">and to:</span></span>

```qsharp
CNOT(control, target);
```