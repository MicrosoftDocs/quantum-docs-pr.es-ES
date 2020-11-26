---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Operación TrotterArbitraryImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 2abfbb9d51a98d8ede1b0835875a3771ffda0691
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204732"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="c5d5b-102">Operación TrotterArbitraryImplCA</span><span class="sxs-lookup"><span data-stu-id="c5d5b-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="c5d5b-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c5d5b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c5d5b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5d5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5d5b-105">Implementación recursiva de Trotter de orden uniforme: integrador de Suzuki.</span><span class="sxs-lookup"><span data-stu-id="c5d5b-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c5d5b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c5d5b-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="c5d5b-107">orden: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5d5b-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5d5b-108">Orden de Trotter-Suzuki integrador.</span><span class="sxs-lookup"><span data-stu-id="c5d5b-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="c5d5b-109">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5d5b-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5d5b-110">El número de operaciones que se van a descomponer en pasos temporales.</span><span class="sxs-lookup"><span data-stu-id="c5d5b-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="c5d5b-111">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c5d5b-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c5d5b-112">Una operación que acepta una entrada de índice (tipo `Int` ) y una entrada de hora (tipo `Double` ) y un registro de Quantum (tipo `'T` ) para la descomposición.</span><span class="sxs-lookup"><span data-stu-id="c5d5b-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c5d5b-113">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c5d5b-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c5d5b-114">Multiplicador en el tamaño de cada paso de la simulación.</span><span class="sxs-lookup"><span data-stu-id="c5d5b-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="c5d5b-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="c5d5b-115">target : 'T</span></span>

<span data-ttu-id="c5d5b-116">Registro de Quantum en el que actúan las operaciones.</span><span class="sxs-lookup"><span data-stu-id="c5d5b-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5d5b-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5d5b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c5d5b-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c5d5b-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5d5b-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="c5d5b-119">'T</span></span>

<span data-ttu-id="c5d5b-120">Tipo en el que debe actuar cada paso de tiempo; Normalmente, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c5d5b-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>