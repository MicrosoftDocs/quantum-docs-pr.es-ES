---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207044"
---
# <a name="embedpauli-function"></a><span data-ttu-id="91cb9-102">EmbedPauli función)</span><span class="sxs-lookup"><span data-stu-id="91cb9-102">EmbedPauli function</span></span>

<span data-ttu-id="91cb9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91cb9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91cb9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91cb9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91cb9-105">Dado un operador Pauli de un solo qubit y el índice de un qubit, devuelve un operador Pauli de varios qubit con el operador Single-qubit dado en dicho índice y `PauliI` en todos los demás índices.</span><span class="sxs-lookup"><span data-stu-id="91cb9-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="91cb9-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="91cb9-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="91cb9-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="91cb9-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="91cb9-108">Un operador Pauli de un solo qubit que se va a colocar en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="91cb9-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="91cb9-109">Ubicación: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91cb9-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91cb9-110">Índice tal que `output[location] == pauli` , donde `output` es la salida de esta función.</span><span class="sxs-lookup"><span data-stu-id="91cb9-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="91cb9-111">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91cb9-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91cb9-112">Longitud de la matriz que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="91cb9-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="91cb9-113">Salida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="91cb9-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

