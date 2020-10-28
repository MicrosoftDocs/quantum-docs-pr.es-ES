---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operación ApplyTransposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733940"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="29292-102">Operación ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="29292-102">ApplyTransposition operation</span></span>

<span data-ttu-id="29292-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="29292-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="29292-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29292-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="29292-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="29292-105">Description</span></span>

<span data-ttu-id="29292-106">Esta operación intercambia la amplitud en el índice `a` con la amplitud en `b` el índice en el vector de estado dado de `register` longitud $n $.</span><span class="sxs-lookup"><span data-stu-id="29292-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="29292-107">Si es `a` igual `b` a, el vector de estado no cambia.</span><span class="sxs-lookup"><span data-stu-id="29292-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="29292-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="29292-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="29292-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="29292-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="29292-110">Primer índice (debe ser un valor comprendido entre 0 y $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="29292-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="29292-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="29292-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="29292-112">Segundo índice (debe ser un valor comprendido entre 0 y $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="29292-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="29292-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="29292-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="29292-114">Una lista de $n $ qubits a la que se aplica la transposición.</span><span class="sxs-lookup"><span data-stu-id="29292-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="29292-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29292-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

