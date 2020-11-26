---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Operación ApplyConditionallyA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 8117fd632b78c24c9ecb8545274eaf296645b645
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230419"
---
# <a name="applyconditionallya-operation"></a>Operación ApplyConditionallyA

Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __no <Result> válido__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __no <Result> válido__[]




### <a name="onequalop--t--unit--is-adj"></a>onEqualOp: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ




### <a name="equalarg--t"></a>equalArg: ' t




### <a name="onnonequalop--u--unit--is-adj"></a>onNonEqualOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada


### <a name="u"></a>' U

