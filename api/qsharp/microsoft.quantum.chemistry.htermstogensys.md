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
# <a name="htermstogensys-function"></a>HTermsToGenSys función)

Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)

Configura [](https://nuget.org/packages/)


Convierte un Hamiltonian en `HTerm[]` formato de datos en un GeneratorSystem.

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="data--hterm"></a>datos: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Datos de entrada en `HTerm[]` formato.


### <a name="termtype--int"></a>Tipo de terminal: [int](xref:microsoft.quantum.lang-ref.int)[]

Información adicional agregada a GeneratorIndex.



## <a name="output--generatorsystem"></a>Salida: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

GeneratorSystem que representa una Hamiltonian representada por la entrada `data` .