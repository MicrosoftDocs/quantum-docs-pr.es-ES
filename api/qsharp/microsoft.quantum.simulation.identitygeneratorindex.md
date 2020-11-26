---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229297"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="33d4f-102">IdentityGeneratorIndex función)</span><span class="sxs-lookup"><span data-stu-id="33d4f-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="33d4f-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="33d4f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="33d4f-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33d4f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33d4f-105">Devuelve un índice de generador coherente con el cero Hamiltonian, `H = 0` , que corresponde a la operación de evolución de identidad.</span><span class="sxs-lookup"><span data-stu-id="33d4f-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="33d4f-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="33d4f-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="33d4f-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="33d4f-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="33d4f-108">Esta entrada se omite y se define para mantener la coherencia con el <xref:microsoft.quantum.simulation.generatorsystem> tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="33d4f-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="33d4f-109">Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="33d4f-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="33d4f-110">Índice de generador que representa la evolución en el $H Hamiltonian = $0.</span><span class="sxs-lookup"><span data-stu-id="33d4f-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>