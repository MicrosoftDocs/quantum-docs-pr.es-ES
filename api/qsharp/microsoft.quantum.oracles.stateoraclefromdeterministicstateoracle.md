---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733341"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="ddd78-102">StateOracleFromDeterministicStateOracle función)</span><span class="sxs-lookup"><span data-stu-id="ddd78-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="ddd78-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ddd78-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ddd78-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ddd78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ddd78-105">Convierte una Oracle de tipo `DeterministicStateOracle` en `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="ddd78-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="ddd78-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ddd78-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="ddd78-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="ddd78-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="ddd78-108">Una preparación de estado de Oracle $A $ de tipo `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="ddd78-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="ddd78-109">Salida: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="ddd78-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="ddd78-110">La misma preparación de estado de Oracle $A $, pero ahora de tipo `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="ddd78-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="ddd78-111">Tenga en cuenta que el índice de marca en esta `StateOracle` es una variable ficticia y no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="ddd78-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddd78-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddd78-112">See Also</span></span>

- [<span data-ttu-id="ddd78-113">Microsoft. Quantum. Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="ddd78-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="ddd78-114">Microsoft. Quantum. Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="ddd78-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)