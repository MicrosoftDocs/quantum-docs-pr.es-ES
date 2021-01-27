---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Operación TrotterArbitraryImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: bb93517a479ce344277bfe97d070e6630a8fccc0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840094"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="c005e-102">Operación TrotterArbitraryImplCA</span><span class="sxs-lookup"><span data-stu-id="c005e-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="c005e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c005e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c005e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c005e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c005e-105">Implementación recursiva de Trotter de orden uniforme: integrador de Suzuki.</span><span class="sxs-lookup"><span data-stu-id="c005e-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c005e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c005e-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="c005e-107">orden: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c005e-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c005e-108">Orden de Trotter-Suzuki integrador.</span><span class="sxs-lookup"><span data-stu-id="c005e-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="c005e-109">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c005e-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c005e-110">El número de operaciones que se van a descomponer en pasos temporales.</span><span class="sxs-lookup"><span data-stu-id="c005e-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="c005e-111">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c005e-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c005e-112">Una operación que acepta una entrada de índice (tipo `Int` ) y una entrada de hora (tipo `Double` ) y un registro de Quantum (tipo `'T` ) para la descomposición.</span><span class="sxs-lookup"><span data-stu-id="c005e-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c005e-113">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c005e-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c005e-114">Multiplicador en el tamaño de cada paso de la simulación.</span><span class="sxs-lookup"><span data-stu-id="c005e-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="c005e-115">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="c005e-115">target : 'T</span></span>

<span data-ttu-id="c005e-116">Registro de Quantum en el que actúan las operaciones.</span><span class="sxs-lookup"><span data-stu-id="c005e-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c005e-117">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c005e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c005e-118">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c005e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c005e-119">Traslada</span><span class="sxs-lookup"><span data-stu-id="c005e-119">'T</span></span>

<span data-ttu-id="c005e-120">Tipo en el que debe actuar cada paso de tiempo; Normalmente, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c005e-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>