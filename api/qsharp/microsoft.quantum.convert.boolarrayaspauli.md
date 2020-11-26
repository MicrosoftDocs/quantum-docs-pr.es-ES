---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: 8e7088ec3918165d7b2afb1056a8319c6fb17796
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214286"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="96aa2-102">BoolArrayAsPauli función)</span><span class="sxs-lookup"><span data-stu-id="96aa2-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="96aa2-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="96aa2-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="96aa2-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="96aa2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="96aa2-105">Dada una cadena de bits, devuelve un operador qubit de Pauli que se representa como una matriz de operadores Pauli de qubit único.</span><span class="sxs-lookup"><span data-stu-id="96aa2-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="96aa2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="96aa2-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="96aa2-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="96aa2-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="96aa2-108">Operador Pauli que se va a aplicar a qubits donde `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="96aa2-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="96aa2-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="96aa2-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="96aa2-110">Aplique Pauli si el bit es este valor.</span><span class="sxs-lookup"><span data-stu-id="96aa2-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="96aa2-111">bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="96aa2-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="96aa2-112">Matriz booleana.</span><span class="sxs-lookup"><span data-stu-id="96aa2-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="96aa2-113">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="96aa2-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="96aa2-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="96aa2-114">Remarks</span></span>

<span data-ttu-id="96aa2-115">La matriz booleana y el registro Quantum deben tener la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="96aa2-115">The Boolean array and the quantum register must be of equal length.</span></span>