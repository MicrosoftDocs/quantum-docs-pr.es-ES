---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsic
title: Operación ApplyIfElseIntrinsic
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsic
qsharp.summary: ''
ms.openlocfilehash: f334c824a48ddc2e0596332b9d58aab2fca982c7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228940"
---
# <a name="applyifelseintrinsic-operation"></a><span data-ttu-id="b425b-102">Operación ApplyIfElseIntrinsic</span><span class="sxs-lookup"><span data-stu-id="b425b-102">ApplyIfElseIntrinsic operation</span></span>

<span data-ttu-id="b425b-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="b425b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b425b-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b425b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsic (measurementResult : Result, onResultZeroOp : (Unit => Unit), onResultOneOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="b425b-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="b425b-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="b425b-106">measurementResult: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="b425b-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit"></a><span data-ttu-id="b425b-107">onResultZeroOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) unidad de unidad</span><span class="sxs-lookup"><span data-stu-id="b425b-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onresultoneop--unit--unit"></a><span data-ttu-id="b425b-108">onResultOneOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) unidad de unidad</span><span class="sxs-lookup"><span data-stu-id="b425b-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="b425b-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b425b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

