---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: Operación ApplyIfOne
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: 0a844e0cd8b4faaa28037985918a4d2d187ebc1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732100"
---
# <a name="applyifone-operation"></a><span data-ttu-id="2b231-102">Operación ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="2b231-102">ApplyIfOne operation</span></span>

<span data-ttu-id="2b231-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="2b231-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="2b231-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b231-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="2b231-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="2b231-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="2b231-106">measurementResult: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="2b231-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="2b231-107">onResultOneOp: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="2b231-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="2b231-108">oneArg: ' t</span><span class="sxs-lookup"><span data-stu-id="2b231-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="2b231-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b231-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2b231-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="2b231-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2b231-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="2b231-111">'T</span></span>

