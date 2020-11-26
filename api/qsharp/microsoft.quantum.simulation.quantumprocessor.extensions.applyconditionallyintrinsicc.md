---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicC
title: Operación ApplyConditionallyIntrinsicC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 847865c04bdaa51cec97826eddcdb95c66001e67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228974"
---
# <a name="applyconditionallyintrinsicc-operation"></a><span data-ttu-id="d3670-102">Operación ApplyConditionallyIntrinsicC</span><span class="sxs-lookup"><span data-stu-id="d3670-102">ApplyConditionallyIntrinsicC operation</span></span>

<span data-ttu-id="d3670-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="d3670-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="d3670-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d3670-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicC (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl), onNonEqualOp : (Unit => Unit is Ctl)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="d3670-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="d3670-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="d3670-106">measurementResults: __no <Result> válido__[]</span><span class="sxs-lookup"><span data-stu-id="d3670-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="d3670-107">resultsValues: __no <Result> válido__[]</span><span class="sxs-lookup"><span data-stu-id="d3670-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-ctl"></a><span data-ttu-id="d3670-108">onEqualOp: la unidad de [unidad](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) es CTL</span><span class="sxs-lookup"><span data-stu-id="d3670-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onnonequalop--unit--unit--is-ctl"></a><span data-ttu-id="d3670-109">onNonEqualOp: la unidad de [unidad](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) es CTL</span><span class="sxs-lookup"><span data-stu-id="d3670-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="d3670-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3670-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

