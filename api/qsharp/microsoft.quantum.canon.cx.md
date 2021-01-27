---
uid: Microsoft.Quantum.Canon.CX
title: Operación de CX
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: e27b30a6b4609daaac2cc5eda68120115777af0c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840756"
---
# <a name="cx-operation"></a><span data-ttu-id="2cddb-102">Operación de CX</span><span class="sxs-lookup"><span data-stu-id="2cddb-102">CX operation</span></span>

<span data-ttu-id="2cddb-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2cddb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2cddb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2cddb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2cddb-105">Aplica la puerta controlada X (CX) a un par de qubits.</span><span class="sxs-lookup"><span data-stu-id="2cddb-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="2cddb-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, donde las filas y columnas están organizadas como en la guía de conceptos de Quantum.</span><span class="sxs-lookup"><span data-stu-id="2cddb-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2cddb-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="2cddb-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="2cddb-108">control: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2cddb-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2cddb-109">Controle qubit para la puerta CX.</span><span class="sxs-lookup"><span data-stu-id="2cddb-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2cddb-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2cddb-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2cddb-111">Destino qubit para la puerta CX.</span><span class="sxs-lookup"><span data-stu-id="2cddb-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2cddb-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2cddb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2cddb-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2cddb-113">Remarks</span></span>

<span data-ttu-id="2cddb-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="2cddb-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="2cddb-115">y para:</span><span class="sxs-lookup"><span data-stu-id="2cddb-115">and to:</span></span>

```qsharp
CNOT(control, target);
```