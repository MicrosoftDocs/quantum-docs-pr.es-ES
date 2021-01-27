---
uid: Microsoft.Quantum.Math._ContinuedFractionConvergentL
title: _ContinuedFractionConvergentL función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: _ContinuedFractionConvergentL
qsharp.summary: Internal recursive call to calculate the GCD with a bound
ms.openlocfilehash: c656b026022b8e4166346bcf82dc4014fdd57834
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851432"
---
# <a name="_continuedfractionconvergentl-function"></a><span data-ttu-id="e9acb-102">_ContinuedFractionConvergentL función)</span><span class="sxs-lookup"><span data-stu-id="e9acb-102">_ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="e9acb-103">Espacio de nombres: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e9acb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e9acb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9acb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9acb-105">Llamada recursiva interna para calcular el M.C. d con un enlazado</span><span class="sxs-lookup"><span data-stu-id="e9acb-105">Internal recursive call to calculate the GCD with a bound</span></span>

```qsharp
function _ContinuedFractionConvergentL (signA : Int, signB : Int, r : (BigInt, BigInt), s : (BigInt, BigInt), t : (BigInt, BigInt), denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="e9acb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e9acb-106">Input</span></span>

### <a name="signa--int"></a><span data-ttu-id="e9acb-107">signA: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9acb-107">signA : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="signb--int"></a><span data-ttu-id="e9acb-108">signB: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9acb-108">signB : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="r--bigintbigint"></a><span data-ttu-id="e9acb-109">r: ([BIGINT](xref:microsoft.quantum.lang-ref.bigint),[BIGINT](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="e9acb-109">r : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="s--bigintbigint"></a><span data-ttu-id="e9acb-110">s: ([BIGINT](xref:microsoft.quantum.lang-ref.bigint),[BIGINT](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="e9acb-110">s : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="t--bigintbigint"></a><span data-ttu-id="e9acb-111">t: ([BIGINT](xref:microsoft.quantum.lang-ref.bigint),[BIGINT](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="e9acb-111">t : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="e9acb-112">denominatorBound: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e9acb-112">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="e9acb-113">Salida: [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="e9acb-113">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

