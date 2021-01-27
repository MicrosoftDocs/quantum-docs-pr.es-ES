---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneC
title: Operación ApplyIfOneC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneC
qsharp.summary: ''
ms.openlocfilehash: ae6e0d16424e745303b377e70927cda847d2f1e8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858734"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="f501f-102">Operación ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="f501f-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="f501f-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="f501f-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f501f-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f501f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneC<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl), oneArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f501f-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="f501f-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="f501f-106">measurementResult: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="f501f-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-ctl"></a><span data-ttu-id="f501f-107">onResultOneOp: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="f501f-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="f501f-108">oneArg: ' t</span><span class="sxs-lookup"><span data-stu-id="f501f-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="f501f-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f501f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f501f-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f501f-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f501f-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="f501f-111">'T</span></span>

