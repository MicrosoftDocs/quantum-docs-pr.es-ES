---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definido por el usuario DeterministicStateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733388"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="9cda6-102">Tipo definido por el usuario DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="9cda6-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="9cda6-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9cda6-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9cda6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9cda6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9cda6-105">Representa una preparación de Oracle para el estado determinista.</span><span class="sxs-lookup"><span data-stu-id="9cda6-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="9cda6-106">La entrada a Oracle $O $ es:</span><span class="sxs-lookup"><span data-stu-id="9cda6-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="9cda6-107">El registro que almacenará el estado de cuanto deseado, $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="9cda6-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="9cda6-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9cda6-108">Remarks</span></span>

<span data-ttu-id="9cda6-109">Este Oracle definido por $O \ket {0} = \ket{\psi} $ actúa en el estado de base de cálculo $ \ket {0} $ para crear el estado $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="9cda6-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="9cda6-110">El primer parámetro es el registro qubit de $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="9cda6-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>