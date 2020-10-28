---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Operación Trotter2ImplCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728331"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="2c70e-102">Operación Trotter2ImplCA</span><span class="sxs-lookup"><span data-stu-id="2c70e-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="2c70e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2c70e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2c70e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c70e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c70e-105">Implementación del Trotter de segundo orden: integrador de Suzuki.</span><span class="sxs-lookup"><span data-stu-id="2c70e-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="2c70e-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2c70e-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="2c70e-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2c70e-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2c70e-108">El número de operaciones que se van a descomponer en pasos temporales.</span><span class="sxs-lookup"><span data-stu-id="2c70e-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="2c70e-109">OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), ' t) => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="2c70e-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2c70e-110">Una operación que acepta una entrada de índice (tipo `Int` ) y una entrada de hora (tipo `Double` ) y un registro de Quantum (tipo `'T` ) para la descomposición.</span><span class="sxs-lookup"><span data-stu-id="2c70e-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="2c70e-111">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2c70e-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2c70e-112">Multiplicador en el tamaño de cada paso de la simulación.</span><span class="sxs-lookup"><span data-stu-id="2c70e-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="2c70e-113">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="2c70e-113">target : 'T</span></span>

<span data-ttu-id="2c70e-114">Registro de Quantum en el que actúan las operaciones.</span><span class="sxs-lookup"><span data-stu-id="2c70e-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c70e-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c70e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2c70e-116">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2c70e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2c70e-117">Traslada</span><span class="sxs-lookup"><span data-stu-id="2c70e-117">'T</span></span>

<span data-ttu-id="2c70e-118">Tipo en el que debe actuar cada paso de tiempo; Normalmente, `Qubit[]` o `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="2c70e-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>