---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851760"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="1f8e5-102">HTermsToGenSys función)</span><span class="sxs-lookup"><span data-stu-id="1f8e5-102">HTermsToGenSys function</span></span>

<span data-ttu-id="1f8e5-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1f8e5-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="1f8e5-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1f8e5-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="1f8e5-105">Convierte un Hamiltonian en `HTerm[]` formato de datos en un GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="1f8e5-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="1f8e5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1f8e5-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="1f8e5-107">datos: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="1f8e5-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="1f8e5-108">Datos de entrada en `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="1f8e5-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="1f8e5-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1f8e5-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1f8e5-110">Información adicional agregada a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="1f8e5-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="1f8e5-111">Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="1f8e5-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="1f8e5-112">GeneratorSystem que representa una Hamiltonian representada por la entrada `data` .</span><span class="sxs-lookup"><span data-stu-id="1f8e5-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>