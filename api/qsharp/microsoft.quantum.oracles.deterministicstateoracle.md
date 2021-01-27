---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definido por el usuario DeterministicStateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842588"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="8bdb4-102">Tipo definido por el usuario DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="8bdb4-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="8bdb4-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="8bdb4-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="8bdb4-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8bdb4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8bdb4-105">Representa una preparación de Oracle para el estado determinista.</span><span class="sxs-lookup"><span data-stu-id="8bdb4-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="8bdb4-106">La entrada a Oracle $O $ es:</span><span class="sxs-lookup"><span data-stu-id="8bdb4-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="8bdb4-107">El registro que almacenará el estado de cuanto deseado, $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="8bdb4-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="8bdb4-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8bdb4-108">Remarks</span></span>

<span data-ttu-id="8bdb4-109">Este Oracle definido por $O \ket {0} = \ket{\psi} $ actúa en el estado de base de cálculo $ \ket {0} $ para crear el estado $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="8bdb4-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="8bdb4-110">El primer parámetro es el registro qubit de $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="8bdb4-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>