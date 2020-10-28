---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727400"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="2b638-102">_prepareEntangledState operación</span><span class="sxs-lookup"><span data-stu-id="2b638-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="2b638-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2b638-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2b638-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b638-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b638-105">Dados dos registros, prepara el estado con una limitación máxima entre cada par de qubits en los registros respectivos.</span><span class="sxs-lookup"><span data-stu-id="2b638-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="2b638-106">Todos los qubits deben comenzar en el estado | 0 ⟩.</span><span class="sxs-lookup"><span data-stu-id="2b638-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="2b638-107">El resultado es que los pares correspondientes de qubits de cada registro se encuentran en $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.</span><span class="sxs-lookup"><span data-stu-id="2b638-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2b638-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="2b638-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="2b638-109">izquierda: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2b638-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2b638-110">Una matriz qubit en el estado $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="2b638-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="2b638-111">Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2b638-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2b638-112">Una matriz qubit en el estado $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="2b638-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b638-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b638-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

