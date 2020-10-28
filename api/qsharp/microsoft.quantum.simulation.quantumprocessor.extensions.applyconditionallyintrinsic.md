---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsic
title: Operación ApplyConditionallyIntrinsic
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsic
qsharp.summary: ''
ms.openlocfilehash: 892e3140544d0b02c5fef085c89c3a4c8bafcde5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730884"
---
# <a name="applyconditionallyintrinsic-operation"></a><span data-ttu-id="58b52-102">Operación ApplyConditionallyIntrinsic</span><span class="sxs-lookup"><span data-stu-id="58b52-102">ApplyConditionallyIntrinsic operation</span></span>

<span data-ttu-id="58b52-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="58b52-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="58b52-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58b52-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsic (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit), onNonEqualOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="58b52-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="58b52-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="58b52-106">measurementResults: __no <Result> válido__ []</span><span class="sxs-lookup"><span data-stu-id="58b52-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="58b52-107">resultsValues: __no <Result> válido__ []</span><span class="sxs-lookup"><span data-stu-id="58b52-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit"></a><span data-ttu-id="58b52-108">onEqualOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) unidad de unidad</span><span class="sxs-lookup"><span data-stu-id="58b52-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onnonequalop--unit--unit"></a><span data-ttu-id="58b52-109">onNonEqualOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) unidad de unidad</span><span class="sxs-lookup"><span data-stu-id="58b52-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="58b52-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58b52-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

