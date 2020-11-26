---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203950"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="2b7a9-102">_ComputeJordanWignerBitString función)</span><span class="sxs-lookup"><span data-stu-id="2b7a9-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="2b7a9-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2b7a9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2b7a9-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2b7a9-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="2b7a9-105">Calcula el componente Z de Jordania – Wigner cadena entre índices Fermion en un operador fermionic con un número par de operadores de creación/Annihilation.</span><span class="sxs-lookup"><span data-stu-id="2b7a9-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="2b7a9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2b7a9-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="2b7a9-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b7a9-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b7a9-108">Número de fermions del sistema.</span><span class="sxs-lookup"><span data-stu-id="2b7a9-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="2b7a9-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2b7a9-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2b7a9-110">índices del operador fermionic.</span><span class="sxs-lookup"><span data-stu-id="2b7a9-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2b7a9-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2b7a9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2b7a9-112">Bitstring `Bool[]` donde se `true` `PauliZ` debe aplicar.</span><span class="sxs-lookup"><span data-stu-id="2b7a9-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>