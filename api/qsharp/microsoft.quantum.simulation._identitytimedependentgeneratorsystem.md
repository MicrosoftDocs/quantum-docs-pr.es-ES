---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726351"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>_IdentityTimeDependentGeneratorSystem función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Configura [](https://nuget.org/packages/)


Devuelve un sistema de generador coherente con Hamiltonian `H(s) = 0` , donde `s` es un parámetro de programación.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="schedule--double"></a>Programación: [doble](xref:microsoft.quantum.lang-ref.double)

Esta entrada se omite y se define para mantener la coherencia con el <xref:microsoft.quantum.canon.timedependentgeneratorsystem> tipo definido por el usuario.



## <a name="output--generatorsystem"></a>Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Un sistema de generación que representa la evolución en el $H (s) Hamiltonian = $0 para todos los $s $.