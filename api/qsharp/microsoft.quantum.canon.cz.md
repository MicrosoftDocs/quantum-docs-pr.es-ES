---
uid: Microsoft.Quantum.Canon.CZ
title: Tarea CZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728775"
---
# <a name="cz-operation"></a><span data-ttu-id="b2eeb-102">Tarea CZ</span><span class="sxs-lookup"><span data-stu-id="b2eeb-102">CZ operation</span></span>

<span data-ttu-id="b2eeb-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b2eeb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b2eeb-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2eeb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2eeb-105">Aplica la puerta controlada-Z (CZ) a un par de qubits.</span><span class="sxs-lookup"><span data-stu-id="b2eeb-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="b2eeb-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $, donde las filas y columnas están organizadas como en la guía de conceptos de Quantum.</span><span class="sxs-lookup"><span data-stu-id="b2eeb-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b2eeb-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="b2eeb-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="b2eeb-108">control: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b2eeb-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b2eeb-109">Controle qubit para la puerta CZ.</span><span class="sxs-lookup"><span data-stu-id="b2eeb-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b2eeb-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b2eeb-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b2eeb-111">Destino qubit para la puerta CZ.</span><span class="sxs-lookup"><span data-stu-id="b2eeb-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2eeb-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2eeb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b2eeb-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b2eeb-113">Remarks</span></span>

<span data-ttu-id="b2eeb-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="b2eeb-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```