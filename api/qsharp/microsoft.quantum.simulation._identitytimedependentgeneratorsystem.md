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
# <a name="_identitytimedependentgeneratorsystem-function"></a>_IdentityTimeDependentGeneratorSystem función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve un sistema de generador coherente con Hamiltonian `H(s) = 0` , donde `s` es un parámetro de programación.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="schedule--double"></a>Programación: [doble](xref:microsoft.quantum.lang-ref.double)

Esta entrada se omite y se define para mantener la coherencia con el <xref:microsoft.quantum.canon.timedependentgeneratorsystem> tipo definido por el usuario.



## <a name="output--generatorsystem"></a>Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Un sistema de generación que representa la evolución en el $H (s) Hamiltonian = $0 para todos los $s $.