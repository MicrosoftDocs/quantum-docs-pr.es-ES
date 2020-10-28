---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728132"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="5d00b-102">HTermsToGenSys función)</span><span class="sxs-lookup"><span data-stu-id="5d00b-102">HTermsToGenSys function</span></span>

<span data-ttu-id="5d00b-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5d00b-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="5d00b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d00b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d00b-105">Convierte un Hamiltonian en `HTerm[]` formato de datos en un GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="5d00b-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="5d00b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5d00b-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="5d00b-107">datos: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="5d00b-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="5d00b-108">Datos de entrada en `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="5d00b-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="5d00b-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5d00b-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5d00b-110">Información adicional agregada a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="5d00b-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="5d00b-111">Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="5d00b-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="5d00b-112">GeneratorSystem que representa una Hamiltonian representada por la entrada `data` .</span><span class="sxs-lookup"><span data-stu-id="5d00b-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>