---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: Operación ApplyConditionallyIntrinsicCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 2dd7a9b6e281c62470defa64685dc58872694468
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230198"
---
# <a name="applyconditionallyintrinsicca-operation"></a>Operación ApplyConditionallyIntrinsicCA

Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __no <Result> válido__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __no <Result> válido__[]




### <a name="onequalop--unit--unit--is-adj--ctl"></a>onEqualOp: la unidad de [unidad](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) es ADJ + CTL




### <a name="onnonequalop--unit--unit--is-adj--ctl"></a>onNonEqualOp: la unidad de [unidad](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) es ADJ + CTL





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

