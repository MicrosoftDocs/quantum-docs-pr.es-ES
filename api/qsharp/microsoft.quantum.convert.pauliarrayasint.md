---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727502"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="365d3-102">PauliArrayAsInt función)</span><span class="sxs-lookup"><span data-stu-id="365d3-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="365d3-103">Espacio de nombres: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="365d3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="365d3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="365d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="365d3-105">Codifica un operador qubit de Pauli que se representa como una matriz de operadores de un solo qubit Pauli en un entero.</span><span class="sxs-lookup"><span data-stu-id="365d3-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="365d3-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="365d3-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="365d3-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="365d3-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="365d3-108">Una matriz de, como máximo, 31 operadores de Pauli de un solo qubit.</span><span class="sxs-lookup"><span data-stu-id="365d3-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="365d3-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="365d3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="365d3-110">Un entero `paulis` que identifica de forma única, tal y como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="365d3-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="365d3-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="365d3-111">Remarks</span></span>

<span data-ttu-id="365d3-112">Cada operador Pauli se puede codificar con dos bits: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="365d3-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="365d3-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="365d3-113">\end{align} $$</span></span>

<span data-ttu-id="365d3-114">Dada una matriz de operadores Pauli `[P0, ..., Pn]` , esta función devuelve un entero con expansión binaria formada mediante la concatenación de las asignaciones de cada operador Pauli en orden Big Endian `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="365d3-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>