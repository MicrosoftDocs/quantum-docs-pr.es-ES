---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847597"
---
# <a name="_deltaparitycnotbitstring-function"></a><span data-ttu-id="f6ba0-102">_DeltaParityCNOTbitstring función)</span><span class="sxs-lookup"><span data-stu-id="f6ba0-102">_DeltaParityCNOTbitstring function</span></span>

<span data-ttu-id="f6ba0-103">Espacio de nombres: [Microsoft. Quantum. Research. química](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f6ba0-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="f6ba0-104">Paquete: [Microsoft. Quantum. Research. química](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f6ba0-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="f6ba0-105">Paso de procesamiento clásico de `ApplyDeltaParity` .</span><span class="sxs-lookup"><span data-stu-id="f6ba0-105">Classical processing step of `ApplyDeltaParity`.</span></span>
<span data-ttu-id="f6ba0-106">Calcula una lista de qubits de control para evaluar la diferencia de paridad entre dos PQRS... términos de longitud uniforme.</span><span class="sxs-lookup"><span data-stu-id="f6ba0-106">This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.</span></span>

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a><span data-ttu-id="f6ba0-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f6ba0-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="f6ba0-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f6ba0-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="nextfermionicterm--int"></a><span data-ttu-id="f6ba0-109">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f6ba0-109">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>





## <a name="output--intbool"></a><span data-ttu-id="f6ba0-110">Salida: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])</span><span class="sxs-lookup"><span data-stu-id="f6ba0-110">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool)[])</span></span>



## <a name="remarks"></a><span data-ttu-id="f6ba0-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f6ba0-111">Remarks</span></span>

<span data-ttu-id="f6ba0-112">Se supone que la longitud de los términos es par.</span><span class="sxs-lookup"><span data-stu-id="f6ba0-112">This assumes that the length of terms is even.</span></span>
<span data-ttu-id="f6ba0-113">Calcula la lista de controles para la diferencia de paridad entre dos términos cualesquiera.</span><span class="sxs-lookup"><span data-stu-id="f6ba0-113">Computes list of controls for parity difference between any two terms.</span></span>
<span data-ttu-id="f6ba0-114">Se supone que las listas de entrada se ordenan en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="f6ba0-114">This assumes that the input lists is sorted in ascending order.</span></span>