---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728138"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="20cf4-102">HTermsToGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="20cf4-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="20cf4-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="20cf4-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="20cf4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20cf4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20cf4-105">Convierte un índice en un término Hamiltonian en `HTerm[]` formato de datos en un GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="20cf4-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="20cf4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="20cf4-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="20cf4-107">datos: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="20cf4-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="20cf4-108">Datos de entrada en `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="20cf4-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="20cf4-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="20cf4-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="20cf4-110">Información adicional agregada a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="20cf4-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="20cf4-111">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="20cf4-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="20cf4-112">Índice para un término de Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="20cf4-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="20cf4-113">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="20cf4-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="20cf4-114">Un GeneratorIndex que representa un término Hamiltonian representado por `data[idx]` , junto con información adicional agregada por `termType` .</span><span class="sxs-lookup"><span data-stu-id="20cf4-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>