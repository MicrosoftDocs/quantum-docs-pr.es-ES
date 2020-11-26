---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225608"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="449c4-102">_IdentityTimeDependentGeneratorSystem función)</span><span class="sxs-lookup"><span data-stu-id="449c4-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="449c4-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="449c4-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="449c4-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="449c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="449c4-105">Devuelve un sistema de generador coherente con Hamiltonian `H(s) = 0` , donde `s` es un parámetro de programación.</span><span class="sxs-lookup"><span data-stu-id="449c4-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="449c4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="449c4-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="449c4-107">Programación: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="449c4-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="449c4-108">Esta entrada se omite y se define para mantener la coherencia con el <xref:microsoft.quantum.canon.timedependentgeneratorsystem> tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="449c4-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="449c4-109">Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="449c4-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="449c4-110">Un sistema de generación que representa la evolución en el $H (s) Hamiltonian = $0 para todos los $s $.</span><span class="sxs-lookup"><span data-stu-id="449c4-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>