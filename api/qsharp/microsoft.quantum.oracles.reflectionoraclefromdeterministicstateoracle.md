---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: 09de63d615a4d80e2b59deeddc07567aefe7660e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193835"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="32075-102">ReflectionOracleFromDeterministicStateOracle función)</span><span class="sxs-lookup"><span data-stu-id="32075-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="32075-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="32075-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="32075-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32075-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32075-105">Construye la reflexión sobre un estado determinado desde Oracle.</span><span class="sxs-lookup"><span data-stu-id="32075-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="32075-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="32075-106">Description</span></span>

<span data-ttu-id="32075-107">Dada una preparación de estado determinista de Oracle representada por una matriz de unitarios $O $, el resultado de esta función es una Oracle que aplica un reflejo en torno al estado $ \ket{\psi} $ preparado por Oracle $O $; es decir, el estado $ \ket{\psi} $, que $O \ket {0} = \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="32075-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="32075-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="32075-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="32075-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="32075-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="32075-110">Oracle que prepara copias del estado $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="32075-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="32075-111">Salida: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="32075-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="32075-112">Oracle que refleja el estado $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="32075-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="32075-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32075-113">See Also</span></span>

- [<span data-ttu-id="32075-114">Microsoft. Quantum. Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="32075-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="32075-115">Microsoft. Quantum. Oracle. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="32075-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)