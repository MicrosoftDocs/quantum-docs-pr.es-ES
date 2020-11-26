---
uid: Microsoft.Quantum.Canon.CZ
title: Tarea CZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207214"
---
# <a name="cz-operation"></a><span data-ttu-id="fe3fa-102">Tarea CZ</span><span class="sxs-lookup"><span data-stu-id="fe3fa-102">CZ operation</span></span>

<span data-ttu-id="fe3fa-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fe3fa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fe3fa-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe3fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe3fa-105">Aplica la puerta controlada-Z (CZ) a un par de qubits.</span><span class="sxs-lookup"><span data-stu-id="fe3fa-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="fe3fa-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $, donde las filas y columnas están organizadas como en la guía de conceptos de Quantum.</span><span class="sxs-lookup"><span data-stu-id="fe3fa-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fe3fa-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="fe3fa-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="fe3fa-108">control: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fe3fa-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fe3fa-109">Controle qubit para la puerta CZ.</span><span class="sxs-lookup"><span data-stu-id="fe3fa-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="fe3fa-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fe3fa-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fe3fa-111">Destino qubit para la puerta CZ.</span><span class="sxs-lookup"><span data-stu-id="fe3fa-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe3fa-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe3fa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fe3fa-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fe3fa-113">Remarks</span></span>

<span data-ttu-id="fe3fa-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="fe3fa-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```