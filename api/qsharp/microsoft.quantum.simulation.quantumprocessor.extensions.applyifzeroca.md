---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: Operación ApplyIfZeroCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: accc3ca9c0d99c48c713333ce1cc907054c2a860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230793"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="077f9-102">Operación ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="077f9-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="077f9-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="077f9-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="077f9-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="077f9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="077f9-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="077f9-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="077f9-106">measurementResult: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="077f9-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="077f9-107">onResultZeroOp: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="077f9-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="077f9-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="077f9-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="077f9-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="077f9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="077f9-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="077f9-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="077f9-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="077f9-111">'T</span></span>

