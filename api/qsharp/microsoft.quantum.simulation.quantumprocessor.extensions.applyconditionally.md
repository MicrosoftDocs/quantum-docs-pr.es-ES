---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Operación ApplyConditionally
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: fe623b240e35ee88f673b6e90db6307ef701d049
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726285"
---
# <a name="applyconditionally-operation"></a>Operación ApplyConditionally

Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Configura [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Entrada

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __no <Result> válido__ []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __no <Result> válido__ []




### <a name="onequalop--t--unit"></a>onEqualOp: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="equalarg--t"></a>equalArg: ' t




### <a name="onnonequalop--u--unit"></a>onNonEqualOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit)> 




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada


### <a name="u"></a>' U

