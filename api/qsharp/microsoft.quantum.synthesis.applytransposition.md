---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operación ApplyTransposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203321"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="3526d-102">Operación ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="3526d-102">ApplyTransposition operation</span></span>

<span data-ttu-id="3526d-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3526d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3526d-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3526d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3526d-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="3526d-105">Description</span></span>

<span data-ttu-id="3526d-106">Esta operación intercambia la amplitud en el índice `a` con la amplitud en `b` el índice en el vector de estado dado de `register` longitud $n $.</span><span class="sxs-lookup"><span data-stu-id="3526d-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="3526d-107">Si es `a` igual `b` a, el vector de estado no cambia.</span><span class="sxs-lookup"><span data-stu-id="3526d-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="3526d-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="3526d-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="3526d-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3526d-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3526d-110">Primer índice (debe ser un valor comprendido entre 0 y $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="3526d-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="3526d-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3526d-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3526d-112">Segundo índice (debe ser un valor comprendido entre 0 y $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="3526d-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3526d-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3526d-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3526d-114">Una lista de $n $ qubits a la que se aplica la transposición.</span><span class="sxs-lookup"><span data-stu-id="3526d-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3526d-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3526d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

