---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726422"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="0cea6-102">_DeltaParityCNOTbitstring función)</span><span class="sxs-lookup"><span data-stu-id="0cea6-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="0cea6-103">Espacio de nombres: [Microsoft. Quantum. Research. química](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0cea6-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="0cea6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0cea6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0cea6-105">Paso de procesamiento clásico de `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="0cea6-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="0cea6-106">Calcula una lista de qubits de control para evaluar la diferencia de paridad entre dos PQRS... términos de longitud uniforme.</span><span class="sxs-lookup"><span data-stu-id="0cea6-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="0cea6-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="0cea6-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="0cea6-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0cea6-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="0cea6-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0cea6-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="0cea6-110">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="0cea6-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="0cea6-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0cea6-111">Remarks</span></span>

<span data-ttu-id="0cea6-112">Se supone que la longitud de los términos es par.</span><span class="sxs-lookup"><span data-stu-id="0cea6-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="0cea6-113">Calcula la lista de controles para la diferencia de paridad entre dos términos cualesquiera.</span><span class="sxs-lookup"><span data-stu-id="0cea6-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="0cea6-114">Se supone que las listas de entrada se ordenan en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="0cea6-114">This assumes that the input lists is sorted in ascending order.</span></span>