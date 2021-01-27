---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Operación Trotter1ImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 6de4b6e7a34d66037d83a6e2bd5821402207c743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840105"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="682c8-102">Operación Trotter1ImplCA</span><span class="sxs-lookup"><span data-stu-id="682c8-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="682c8-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="682c8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="682c8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="682c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="682c8-105">Implementación del Trotter de primer orden: integrador de Suzuki.</span><span class="sxs-lookup"><span data-stu-id="682c8-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="682c8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="682c8-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="682c8-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="682c8-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="682c8-108">El número de operaciones que se van a descomponer en pasos temporales.</span><span class="sxs-lookup"><span data-stu-id="682c8-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="682c8-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="682c8-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="682c8-110">Una operación que acepta una entrada de índice (tipo `Int` ) y una entrada de hora (tipo `Double` ) y un registro de Quantum (tipo `'T` ) para la descomposición.</span><span class="sxs-lookup"><span data-stu-id="682c8-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="682c8-111">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="682c8-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="682c8-112">Multiplicador en el tamaño de cada paso de la simulación.</span><span class="sxs-lookup"><span data-stu-id="682c8-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="682c8-113">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="682c8-113">target : 'T</span></span>

<span data-ttu-id="682c8-114">Registro de Quantum en el que actúan las operaciones.</span><span class="sxs-lookup"><span data-stu-id="682c8-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="682c8-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="682c8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="682c8-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="682c8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="682c8-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="682c8-117">'T</span></span>

<span data-ttu-id="682c8-118">Tipo en el que debe actuar cada paso de tiempo; Normalmente, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="682c8-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="682c8-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="682c8-119">Example</span></span>

<span data-ttu-id="682c8-120">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="682c8-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT, target);
op(1, deltaT, target);
```

<span data-ttu-id="682c8-121">y</span><span class="sxs-lookup"><span data-stu-id="682c8-121">and</span></span>

```qsharp
Trotter1ImplCA((2, op), deltaT, target);
```