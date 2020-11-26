---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: Operación ApplyConditionallyA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 8117fd632b78c24c9ecb8545274eaf296645b645
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230419"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="d80d1-102">Operación ApplyConditionallyA</span><span class="sxs-lookup"><span data-stu-id="d80d1-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="d80d1-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="d80d1-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="d80d1-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d80d1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="d80d1-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="d80d1-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="d80d1-106">measurementResults: __no <Result> válido__[]</span><span class="sxs-lookup"><span data-stu-id="d80d1-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="d80d1-107">resultsValues: __no <Result> válido__[]</span><span class="sxs-lookup"><span data-stu-id="d80d1-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="d80d1-108">onEqualOp: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="d80d1-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="d80d1-109">equalArg: ' t</span><span class="sxs-lookup"><span data-stu-id="d80d1-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="d80d1-110">onNonEqualOp: ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="d80d1-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="d80d1-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="d80d1-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="d80d1-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d80d1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d80d1-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="d80d1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d80d1-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="d80d1-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="d80d1-115">' U</span><span class="sxs-lookup"><span data-stu-id="d80d1-115">'U</span></span>

