---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operación ApplyDeltaParity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225761"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="cb157-102">Operación ApplyDeltaParity</span><span class="sxs-lookup"><span data-stu-id="cb157-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="cb157-103">Espacio de nombres: [Microsoft. Quantum. Research. química](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cb157-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="cb157-104">Paquete: [Microsoft. Quantum. Research. química](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cb157-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="cb157-105">Calcula la diferencia en la paridad entre un PQRS anterior... términos y el siguiente PQRS... plazo.</span><span class="sxs-lookup"><span data-stu-id="cb157-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="cb157-106">Esta diferencia se calcula en un qubit auxiliar.</span><span class="sxs-lookup"><span data-stu-id="cb157-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cb157-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cb157-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="cb157-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cb157-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cb157-109">Lista de índices para el PQRS anterior... terminología.</span><span class="sxs-lookup"><span data-stu-id="cb157-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="cb157-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cb157-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cb157-111">Lista de índices para el siguiente PQRS... terminología.</span><span class="sxs-lookup"><span data-stu-id="cb157-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="cb157-112">AUX: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cb157-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cb157-113">Qubit auxiliar en el que se almacenan los resultados de cálculo de paridad.</span><span class="sxs-lookup"><span data-stu-id="cb157-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cb157-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cb157-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cb157-115">Qubit actuó por todos los PQRS... terminología.</span><span class="sxs-lookup"><span data-stu-id="cb157-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb157-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb157-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cb157-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb157-117">Remarks</span></span>

<span data-ttu-id="cb157-118">Se supone que los índices de P < Q < R < S <... tanto para prevPQ como para nextPQ.</span><span class="sxs-lookup"><span data-stu-id="cb157-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>