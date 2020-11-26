---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204120"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="6a947-102">HTermsToGenSys función)</span><span class="sxs-lookup"><span data-stu-id="6a947-102">HTermsToGenSys function</span></span>

<span data-ttu-id="6a947-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6a947-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="6a947-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6a947-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6a947-105">Convierte un Hamiltonian en `HTerm[]` formato de datos en un GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="6a947-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="6a947-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="6a947-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="6a947-107">datos: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="6a947-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="6a947-108">Datos de entrada en `HTerm[]` formato.</span><span class="sxs-lookup"><span data-stu-id="6a947-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="6a947-109">Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6a947-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6a947-110">Información adicional agregada a GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="6a947-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="6a947-111">Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="6a947-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="6a947-112">GeneratorSystem que representa una Hamiltonian representada por la entrada `data` .</span><span class="sxs-lookup"><span data-stu-id="6a947-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>