---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Tipo definido por el usuario StateOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733348"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="91ba3-102">Tipo definido por el usuario StateOracle</span><span class="sxs-lookup"><span data-stu-id="91ba3-102">StateOracle user defined type</span></span>

<span data-ttu-id="91ba3-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="91ba3-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="91ba3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91ba3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91ba3-105">Representa una preparación de Oracle para el estado.</span><span class="sxs-lookup"><span data-stu-id="91ba3-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="91ba3-106">Las entradas a Oracle $O $ son:</span><span class="sxs-lookup"><span data-stu-id="91ba3-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="91ba3-107">Un entero que indiza la marca qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="91ba3-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="91ba3-108">El registro del sistema $s $ que almacenará el estado de cuanto deseado, $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="91ba3-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="91ba3-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91ba3-109">Remarks</span></span>

<span data-ttu-id="91ba3-110">Este Oracle definido por $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ actúa sobre el estado de base de cálculo $ \ket {0} \_ {f} \ket {0} \_ s $ para crear el estado de destino $ \ket{\psi} \_ s $ con amplitud $ \lambda $ en la base marcada por $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="91ba3-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="91ba3-111">El primer parámetro es un índice del registro qubit de $ \ket {0} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="91ba3-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="91ba3-112">El segundo parámetro engloba ambos registros.</span><span class="sxs-lookup"><span data-stu-id="91ba3-112">The second parameter encompassed both registers.</span></span>