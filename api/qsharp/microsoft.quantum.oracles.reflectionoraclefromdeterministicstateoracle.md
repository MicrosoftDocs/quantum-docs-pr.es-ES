---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732180"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="9a4c5-102">ReflectionOracleFromDeterministicStateOracle función)</span><span class="sxs-lookup"><span data-stu-id="9a4c5-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="9a4c5-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9a4c5-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9a4c5-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a4c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a4c5-105">Construye la reflexión sobre un estado determinado desde Oracle.</span><span class="sxs-lookup"><span data-stu-id="9a4c5-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="9a4c5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a4c5-106">Description</span></span>

<span data-ttu-id="9a4c5-107">Dada una preparación de estado determinista de Oracle representada por una matriz de unitarios $O $, el resultado de esta función es una Oracle que aplica un reflejo en torno al estado $ \ket{\psi} $ preparado por Oracle $O $; es decir, el estado $ \ket{\psi} $, que $O \ket {0} = \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="9a4c5-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="9a4c5-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="9a4c5-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="9a4c5-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="9a4c5-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="9a4c5-110">Oracle que prepara copias del estado $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="9a4c5-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="9a4c5-111">Salida: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="9a4c5-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="9a4c5-112">Oracle que refleja el estado $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="9a4c5-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a4c5-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a4c5-113">See Also</span></span>

- [<span data-ttu-id="9a4c5-114">Microsoft. Quantum. Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="9a4c5-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="9a4c5-115">Microsoft. Quantum. Oracle. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="9a4c5-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)