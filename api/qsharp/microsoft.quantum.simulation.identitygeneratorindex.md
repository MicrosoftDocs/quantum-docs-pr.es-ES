---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733525"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="2ad6d-102">IdentityGeneratorIndex función)</span><span class="sxs-lookup"><span data-stu-id="2ad6d-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="2ad6d-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2ad6d-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2ad6d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2ad6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2ad6d-105">Devuelve un índice de generador coherente con el cero Hamiltonian, `H = 0` , que corresponde a la operación de evolución de identidad.</span><span class="sxs-lookup"><span data-stu-id="2ad6d-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="2ad6d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="2ad6d-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="2ad6d-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2ad6d-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2ad6d-108">Esta entrada se omite y se define para mantener la coherencia con el <xref:microsoft.quantum.simulation.generatorsystem> tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="2ad6d-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="2ad6d-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2ad6d-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2ad6d-110">Índice de generador que representa la evolución en el $H Hamiltonian = $0.</span><span class="sxs-lookup"><span data-stu-id="2ad6d-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>