---
uid: Microsoft.Quantum.Canon.CX
title: Operación de CX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4eaecf372f3054de4886b1e42c6b4ce386a22f73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207248"
---
# <a name="cx-operation"></a><span data-ttu-id="a3197-102">Operación de CX</span><span class="sxs-lookup"><span data-stu-id="a3197-102">CX operation</span></span>

<span data-ttu-id="a3197-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a3197-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a3197-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3197-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3197-105">Aplica la puerta controlada X (CX) a un par de qubits.</span><span class="sxs-lookup"><span data-stu-id="a3197-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="a3197-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, donde las filas y columnas están organizadas como en la guía de conceptos de Quantum.</span><span class="sxs-lookup"><span data-stu-id="a3197-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a3197-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="a3197-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="a3197-108">control: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a3197-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a3197-109">Controle qubit para la puerta CX.</span><span class="sxs-lookup"><span data-stu-id="a3197-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a3197-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a3197-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a3197-111">Destino qubit para la puerta CX.</span><span class="sxs-lookup"><span data-stu-id="a3197-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3197-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3197-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a3197-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a3197-113">Remarks</span></span>

<span data-ttu-id="a3197-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="a3197-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="a3197-115">y para:</span><span class="sxs-lookup"><span data-stu-id="a3197-115">and to:</span></span>

```qsharp
CNOT(control, target);
```