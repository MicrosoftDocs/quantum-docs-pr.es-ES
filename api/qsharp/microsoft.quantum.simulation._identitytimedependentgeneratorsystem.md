---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857983"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="3c2e0-102">_IdentityTimeDependentGeneratorSystem función)</span><span class="sxs-lookup"><span data-stu-id="3c2e0-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="3c2e0-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3c2e0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3c2e0-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c2e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c2e0-105">Devuelve un sistema de generador coherente con Hamiltonian `H(s) = 0` , donde `s` es un parámetro de programación.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="3c2e0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3c2e0-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="3c2e0-107">Programación: [doble](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3c2e0-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3c2e0-108">Esta entrada se omite y se define para mantener la coherencia con el <xref:microsoft.quantum.canon.timedependentgeneratorsystem> tipo definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="3c2e0-109">Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3c2e0-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3c2e0-110">Un sistema de generación que representa la evolución en el $H (s) Hamiltonian = $0 para todos los $s $.</span><span class="sxs-lookup"><span data-stu-id="3c2e0-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>