---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224248"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="55c6e-102">PauliArrayAsInt función)</span><span class="sxs-lookup"><span data-stu-id="55c6e-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="55c6e-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="55c6e-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="55c6e-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="55c6e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="55c6e-105">Codifica un operador qubit de Pauli que se representa como una matriz de operadores de un solo qubit Pauli en un entero.</span><span class="sxs-lookup"><span data-stu-id="55c6e-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="55c6e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="55c6e-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="55c6e-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="55c6e-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="55c6e-108">Una matriz de, como máximo, 31 operadores de Pauli de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="55c6e-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="55c6e-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55c6e-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55c6e-110">Un entero `paulis` que identifica de forma única, tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="55c6e-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="55c6e-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="55c6e-111">Remarks</span></span>

<span data-ttu-id="55c6e-112">Cada operador Pauli se puede codificar con dos bits: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="55c6e-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="55c6e-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="55c6e-113">\end{align} $$</span></span>

<span data-ttu-id="55c6e-114">Dada una matriz de operadores Pauli `[P0, ..., Pn]` , esta función devuelve un entero con expansión binaria formada mediante la concatenación de las asignaciones de cada operador Pauli en orden Big Endian `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="55c6e-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>