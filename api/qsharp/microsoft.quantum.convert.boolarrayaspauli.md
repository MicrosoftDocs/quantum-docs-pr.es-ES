---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834247"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="8c3a5-102">BoolArrayAsPauli función)</span><span class="sxs-lookup"><span data-stu-id="8c3a5-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="8c3a5-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="8c3a5-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="8c3a5-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8c3a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8c3a5-105">Dada una cadena de bits, devuelve un operador qubit de Pauli que se representa como una matriz de operadores Pauli de qubit único.</span><span class="sxs-lookup"><span data-stu-id="8c3a5-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="8c3a5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="8c3a5-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="8c3a5-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="8c3a5-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="8c3a5-108">Operador Pauli que se va a aplicar a qubits donde `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="8c3a5-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="8c3a5-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8c3a5-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8c3a5-110">Aplique Pauli si el bit es este valor.</span><span class="sxs-lookup"><span data-stu-id="8c3a5-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="8c3a5-111">bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="8c3a5-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="8c3a5-112">Matriz booleana.</span><span class="sxs-lookup"><span data-stu-id="8c3a5-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="8c3a5-113">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="8c3a5-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="8c3a5-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8c3a5-114">Remarks</span></span>

<span data-ttu-id="8c3a5-115">La matriz booleana y el registro Quantum deben tener la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="8c3a5-115">The Boolean array and the quantum register must be of equal length.</span></span>