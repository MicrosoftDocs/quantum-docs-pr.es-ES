---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Operación ApplyConditionallyC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 09496d384a70fa9fb6826304ce9909034297a118
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847851"
---
# <a name="applyconditionallyc-operation"></a><span data-ttu-id="0db5a-102">Operación ApplyConditionallyC</span><span class="sxs-lookup"><span data-stu-id="0db5a-102">ApplyConditionallyC operation</span></span>

<span data-ttu-id="0db5a-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="0db5a-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="0db5a-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0db5a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="0db5a-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="0db5a-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="0db5a-106">measurementResults: __no <Result> válido__[]</span><span class="sxs-lookup"><span data-stu-id="0db5a-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="0db5a-107">resultsValues: __no <Result> válido__[]</span><span class="sxs-lookup"><span data-stu-id="0db5a-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-ctl"></a><span data-ttu-id="0db5a-108">onEqualOp: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="0db5a-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="0db5a-109">equalArg: ' t</span><span class="sxs-lookup"><span data-stu-id="0db5a-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-ctl"></a><span data-ttu-id="0db5a-110">onNonEqualOp: ' U => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="0db5a-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="0db5a-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="0db5a-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="0db5a-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0db5a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0db5a-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0db5a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0db5a-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="0db5a-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="0db5a-115">' U</span><span class="sxs-lookup"><span data-stu-id="0db5a-115">'U</span></span>

