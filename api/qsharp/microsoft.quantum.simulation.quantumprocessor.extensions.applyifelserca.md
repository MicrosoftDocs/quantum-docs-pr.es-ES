---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: Operación ApplyIfElseRCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: 2f72da8b470e340d8b283a27643797d41b44592e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855623"
---
# <a name="applyifelserca-operation"></a>Operación ApplyIfElseRCA

Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __no <Result> válido__




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a>onResultZeroOp: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL




### <a name="zeroarg--t"></a>zeroArg: ' t




### <a name="onresultoneop--u--unit--is-adj--ctl"></a>onResultOneOp: ' U => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL




### <a name="onearg--u"></a>oneArg: ' U





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada


### <a name="u"></a>' U

