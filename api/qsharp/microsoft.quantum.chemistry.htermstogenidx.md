---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839623"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="bf099-102">HTermsToGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="bf099-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="bf099-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bf099-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="bf099-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="bf099-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="bf099-105">Convierte un índice en un término Hamiltonian en `HTerm[]` formato de datos en un GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="bf099-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="bf099-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bf099-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="bf099-107">datos: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="bf099-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="bf099-108">Datos de entrada en `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="bf099-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="bf099-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bf099-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="bf099-110">Información adicional agregada a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="bf099-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="bf099-111">IDX: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bf099-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bf099-112">Índice para un término de Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="bf099-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="bf099-113">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="bf099-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="bf099-114">Un GeneratorIndex que representa un término Hamiltonian representado por `data[idx]` , junto con información adicional agregada por `termType` .</span><span class="sxs-lookup"><span data-stu-id="bf099-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>