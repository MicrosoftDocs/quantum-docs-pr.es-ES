---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: Operación ApplyIfZero
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: f0c8cfc2292cf30ee3ab86c486e982347086453b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858275"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="24819-102">Operación ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="24819-102">ApplyIfZero operation</span></span>

<span data-ttu-id="24819-103">Espacio de nombres: [Microsoft. Quantum. Simulation. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="24819-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="24819-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="24819-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="24819-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="24819-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="24819-106">measurementResult: __no <Result> válido__</span><span class="sxs-lookup"><span data-stu-id="24819-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="24819-107">onResultZeroOp: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="24819-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="24819-108">zeroArg: ' t</span><span class="sxs-lookup"><span data-stu-id="24819-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="24819-109">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24819-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="24819-110">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="24819-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="24819-111">Traslada</span><span class="sxs-lookup"><span data-stu-id="24819-111">'T</span></span>

