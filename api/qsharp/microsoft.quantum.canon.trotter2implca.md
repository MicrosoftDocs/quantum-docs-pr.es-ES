---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Operación Trotter2ImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 34b60934b67c19b2d1d718d68b85a2f0fffeab5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852014"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="dc001-102">Operación Trotter2ImplCA</span><span class="sxs-lookup"><span data-stu-id="dc001-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="dc001-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc001-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc001-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc001-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc001-105">Implementación del Trotter de segundo orden: integrador de Suzuki.</span><span class="sxs-lookup"><span data-stu-id="dc001-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dc001-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dc001-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="dc001-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc001-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc001-108">El número de operaciones que se van a descomponer en pasos temporales.</span><span class="sxs-lookup"><span data-stu-id="dc001-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="dc001-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="dc001-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dc001-110">Una operación que acepta una entrada de índice (tipo `Int` ) y una entrada de hora (tipo `Double` ) y un registro de Quantum (tipo `'T` ) para la descomposición.</span><span class="sxs-lookup"><span data-stu-id="dc001-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="dc001-111">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dc001-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dc001-112">Multiplicador en el tamaño de cada paso de la simulación.</span><span class="sxs-lookup"><span data-stu-id="dc001-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="dc001-113">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="dc001-113">target : 'T</span></span>

<span data-ttu-id="dc001-114">Registro de Quantum en el que actúan las operaciones.</span><span class="sxs-lookup"><span data-stu-id="dc001-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc001-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc001-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dc001-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="dc001-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc001-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="dc001-117">'T</span></span>

<span data-ttu-id="dc001-118">Tipo en el que debe actuar cada paso de tiempo; Normalmente, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="dc001-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="dc001-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc001-119">Example</span></span>

<span data-ttu-id="dc001-120">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="dc001-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(0, deltaT / 2.0, target);
```

<span data-ttu-id="dc001-121">y</span><span class="sxs-lookup"><span data-stu-id="dc001-121">and</span></span>

```qsharp
Trotter2ImplCA((2, op), deltaT, target);
```