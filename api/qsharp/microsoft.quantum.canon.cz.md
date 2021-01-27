---
uid: Microsoft.Quantum.Canon.CZ
title: Tarea CZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: cef1544fb76d561cfd0949c84c487550d523bb85
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840701"
---
# <a name="cz-operation"></a><span data-ttu-id="de0b2-102">Tarea CZ</span><span class="sxs-lookup"><span data-stu-id="de0b2-102">CZ operation</span></span>

<span data-ttu-id="de0b2-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="de0b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="de0b2-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de0b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de0b2-105">Aplica la puerta controlada-Z (CZ) a un par de qubits.</span><span class="sxs-lookup"><span data-stu-id="de0b2-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="de0b2-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $, donde las filas y columnas están organizadas como en la guía de conceptos de Quantum.</span><span class="sxs-lookup"><span data-stu-id="de0b2-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="de0b2-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="de0b2-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="de0b2-108">control: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="de0b2-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="de0b2-109">Controle qubit para la puerta CZ.</span><span class="sxs-lookup"><span data-stu-id="de0b2-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="de0b2-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="de0b2-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="de0b2-111">Destino qubit para la puerta CZ.</span><span class="sxs-lookup"><span data-stu-id="de0b2-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de0b2-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de0b2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="de0b2-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="de0b2-113">Remarks</span></span>

<span data-ttu-id="de0b2-114">Equivalente a:</span><span class="sxs-lookup"><span data-stu-id="de0b2-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```