---
uid: Microsoft.Quantum.Canon.CY
title: Operación CY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728781"
---
# <a name="cy-operation"></a><span data-ttu-id="16e24-102">Operación CY</span><span class="sxs-lookup"><span data-stu-id="16e24-102">CY operation</span></span>

<span data-ttu-id="16e24-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="16e24-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="16e24-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="16e24-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="16e24-105">Aplica la puerta controlada-Y (CY) a un par de qubits.</span><span class="sxs-lookup"><span data-stu-id="16e24-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="16e24-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -i \\ \\ 0 & 0 & i & 0 \end{align}, $ $, donde las filas y columnas están organizadas como en la guía de conceptos de Quantum.</span><span class="sxs-lookup"><span data-stu-id="16e24-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="16e24-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="16e24-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="16e24-108">control: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="16e24-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="16e24-109">Controle qubit para la puerta CY.</span><span class="sxs-lookup"><span data-stu-id="16e24-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="16e24-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="16e24-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="16e24-111">Qubit de destino para la puerta CY.</span><span class="sxs-lookup"><span data-stu-id="16e24-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="16e24-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16e24-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="16e24-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="16e24-113">Remarks</span></span>

<span data-ttu-id="16e24-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="16e24-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```