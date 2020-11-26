---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 8f1fe34e38edefba228fb9d01e1712e4c0916970
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226696"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="32ecb-102">ObliviousOracleFromDeterministicStateOracle función)</span><span class="sxs-lookup"><span data-stu-id="32ecb-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="32ecb-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="32ecb-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="32ecb-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32ecb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32ecb-105">Combina Oracle `DeterministicStateOracle` y `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="32ecb-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="32ecb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="32ecb-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="32ecb-107">ancillaOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="32ecb-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="32ecb-108">Una preparación de estado Oracle $A $ de tipo que `DeterministicStateOracle` actúa sobre el registro $a $.</span><span class="sxs-lookup"><span data-stu-id="32ecb-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="32ecb-109">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="32ecb-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="32ecb-110">Un Oracle $U $ de tipo que `ObliviousOracle` actúa conjuntamente en el registro $a, s $.</span><span class="sxs-lookup"><span data-stu-id="32ecb-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="32ecb-111">Salida: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="32ecb-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="32ecb-112">Un $O de Oracle = UA $ de tipo `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="32ecb-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="32ecb-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32ecb-113">See Also</span></span>

- [<span data-ttu-id="32ecb-114">Microsoft. Quantum. Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="32ecb-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="32ecb-115">Microsoft. Quantum. Oracle. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="32ecb-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)