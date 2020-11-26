---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: Operación ApplyIfElseRC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 33b3adfca87410480108eafd090632006117f7b2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192645"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="bc7bc-102">Operación ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="bc7bc-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="bc7bc-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="bc7bc-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="bc7bc-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bc7bc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="bc7bc-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="bc7bc-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="bc7bc-106">measurementResult: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="bc7bc-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="bc7bc-107">onResultZeroOp: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="bc7bc-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="bc7bc-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="bc7bc-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-ctl"></a><span data-ttu-id="bc7bc-109">onResultOneOp: ' U => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="bc7bc-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="bc7bc-110">oneArg: ' U</span><span class="sxs-lookup"><span data-stu-id="bc7bc-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="bc7bc-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc7bc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc7bc-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="bc7bc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc7bc-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="bc7bc-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="bc7bc-114">' U</span><span class="sxs-lookup"><span data-stu-id="bc7bc-114">'U</span></span>

