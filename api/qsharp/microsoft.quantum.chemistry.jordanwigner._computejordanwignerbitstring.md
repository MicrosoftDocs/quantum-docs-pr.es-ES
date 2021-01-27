---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839528"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="9daab-102">_ComputeJordanWignerBitString función)</span><span class="sxs-lookup"><span data-stu-id="9daab-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="9daab-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="9daab-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="9daab-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9daab-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="9daab-105">Calcula el componente Z de Jordania – Wigner cadena entre índices Fermion en un operador fermionic con un número par de operadores de creación/Annihilation.</span><span class="sxs-lookup"><span data-stu-id="9daab-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="9daab-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9daab-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="9daab-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9daab-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9daab-108">Número de fermions del sistema.</span><span class="sxs-lookup"><span data-stu-id="9daab-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="9daab-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9daab-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9daab-110">índices del operador fermionic.</span><span class="sxs-lookup"><span data-stu-id="9daab-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9daab-111">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="9daab-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="9daab-112">Bitstring `Bool[]` donde se `true` `PauliZ` debe aplicar.</span><span class="sxs-lookup"><span data-stu-id="9daab-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>

## <a name="example"></a><span data-ttu-id="9daab-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9daab-113">Example</span></span>

<span data-ttu-id="9daab-114">Let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]); bitString es [false, false, false, true, true, true, false].</span><span class="sxs-lookup"><span data-stu-id="9daab-114">let bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]) ; // bitString is [false, false, false ,true, true, true, false].</span></span>