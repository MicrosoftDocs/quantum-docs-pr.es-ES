---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728127"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="23eb7-102">HTermToGenIdx función)</span><span class="sxs-lookup"><span data-stu-id="23eb7-102">HTermToGenIdx function</span></span>

<span data-ttu-id="23eb7-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="23eb7-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="23eb7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23eb7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23eb7-105">Convierte un término Hamiltonian en `HTerm` formato de datos en un GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="23eb7-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="23eb7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="23eb7-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="23eb7-107">término: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="23eb7-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="23eb7-108">Datos de entrada en `HTerm` formato.</span><span class="sxs-lookup"><span data-stu-id="23eb7-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="23eb7-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="23eb7-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="23eb7-110">Información adicional agregada a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="23eb7-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="23eb7-111">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="23eb7-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="23eb7-112">Un GeneratorIndex que representa un término Hamiltonian representado por `term` , junto con información adicional agregada por `termType` .</span><span class="sxs-lookup"><span data-stu-id="23eb7-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>