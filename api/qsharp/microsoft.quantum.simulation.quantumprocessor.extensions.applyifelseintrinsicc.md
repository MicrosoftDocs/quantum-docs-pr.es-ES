---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicC
title: Operación ApplyIfElseIntrinsicC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 178d4b704d84090f1f8592b857c3da659e5c50bb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733668"
---
# <a name="applyifelseintrinsicc-operation"></a><span data-ttu-id="dde76-102">Operación ApplyIfElseIntrinsicC</span><span class="sxs-lookup"><span data-stu-id="dde76-102">ApplyIfElseIntrinsicC operation</span></span>

<span data-ttu-id="dde76-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="dde76-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="dde76-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dde76-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseIntrinsicC (measurementResult : Result, onResultZeroOp : (Unit => Unit is Ctl), onResultOneOp : (Unit => Unit is Ctl)) : Unit
```


## <a name="input"></a><span data-ttu-id="dde76-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="dde76-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="dde76-106">measurementResult: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="dde76-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit-ctl"></a><span data-ttu-id="dde76-107">onResultZeroOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit) de unidad</span><span class="sxs-lookup"><span data-stu-id="dde76-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onresultoneop--unit--unit-ctl"></a><span data-ttu-id="dde76-108">onResultOneOp: [Unit](xref:microsoft.quantum.lang-ref.unit) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit) de unidad</span><span class="sxs-lookup"><span data-stu-id="dde76-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="dde76-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dde76-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

