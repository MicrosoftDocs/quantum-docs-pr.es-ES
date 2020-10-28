---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: Operación PrepareEntangledState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732173"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="cd4a8-102">Operación PrepareEntangledState</span><span class="sxs-lookup"><span data-stu-id="cd4a8-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="cd4a8-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="cd4a8-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="cd4a8-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd4a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd4a8-105">En pares de dos registros qubit.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="cd4a8-106">Es decir, dados dos registros, prepara el estado de in\frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ entre cada par de qubits en los respectivos registros, suponiendo que cada registro comienza en el estado $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="cd4a8-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cd4a8-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cd4a8-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="cd4a8-108">izquierda: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cd4a8-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cd4a8-109">Una matriz qubit en el estado $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="cd4a8-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="cd4a8-110">Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cd4a8-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cd4a8-111">Una matriz qubit en el estado $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="cd4a8-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd4a8-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd4a8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

