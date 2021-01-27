---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: Operación ApplyDeltaParity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851109"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="986ec-102">Operación ApplyDeltaParity</span><span class="sxs-lookup"><span data-stu-id="986ec-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="986ec-103">Espacio de nombres: [Microsoft. Quantum. Research. química](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="986ec-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="986ec-104">Paquete: [Microsoft. Quantum. Research. química](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="986ec-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="986ec-105">Calcula la diferencia en la paridad entre un PQRS anterior... términos y el siguiente PQRS... plazo.</span><span class="sxs-lookup"><span data-stu-id="986ec-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="986ec-106">Esta diferencia se calcula en un qubit auxiliar.</span><span class="sxs-lookup"><span data-stu-id="986ec-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="986ec-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="986ec-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="986ec-108">prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="986ec-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="986ec-109">Lista de índices para el PQRS anterior... terminología.</span><span class="sxs-lookup"><span data-stu-id="986ec-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="986ec-110">nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="986ec-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="986ec-111">Lista de índices para el siguiente PQRS... terminología.</span><span class="sxs-lookup"><span data-stu-id="986ec-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="986ec-112">AUX: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="986ec-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="986ec-113">Qubit auxiliar en el que se almacenan los resultados de cálculo de paridad.</span><span class="sxs-lookup"><span data-stu-id="986ec-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="986ec-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="986ec-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="986ec-115">Qubit actuó por todos los PQRS... terminología.</span><span class="sxs-lookup"><span data-stu-id="986ec-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="986ec-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="986ec-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="986ec-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="986ec-117">Remarks</span></span>

<span data-ttu-id="986ec-118">Se supone que los índices de P < Q < R < S <... tanto para prevPQ como para nextPQ.</span><span class="sxs-lookup"><span data-stu-id="986ec-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>