---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Operación ApplyBlockEncodingByLCU
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732148"
---
# <a name="applyblockencodingbylcu-operation"></a>Operación ApplyBlockEncodingByLCU

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Configura [](https://nuget.org/packages/)


Implementación de `BlockEncodingByLCU`.

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a>Entrada

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="selector--ts--unit-adj--ctl"></a>Selector: (' t, ') => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL




### <a name="auxiliary--t"></a>auxiliar: ' t '




### <a name="system--s"></a>sistema:





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada


### <a name="s"></a>Hoy

