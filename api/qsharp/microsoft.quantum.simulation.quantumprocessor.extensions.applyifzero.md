---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: Operación ApplyIfZero
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: 867e2e78ea787c2376fb2b1dcc6c72694fe08621
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230912"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="469b3-102">Operación ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="469b3-102">ApplyIfZero operation</span></span>

<span data-ttu-id="469b3-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="469b3-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="469b3-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="469b3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="469b3-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="469b3-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="469b3-106">measurementResult: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="469b3-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="469b3-107">onResultZeroOp: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="469b3-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="469b3-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="469b3-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="469b3-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="469b3-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="469b3-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="469b3-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="469b3-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="469b3-111">'T</span></span>

