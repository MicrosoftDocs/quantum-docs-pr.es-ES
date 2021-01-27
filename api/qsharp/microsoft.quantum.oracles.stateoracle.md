---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Tipo definido por el usuario StateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854462"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="bb62b-102">Tipo definido por el usuario StateOracle</span><span class="sxs-lookup"><span data-stu-id="bb62b-102">StateOracle user defined type</span></span>

<span data-ttu-id="bb62b-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="bb62b-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="bb62b-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bb62b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bb62b-105">Representa una preparación de Oracle para el estado.</span><span class="sxs-lookup"><span data-stu-id="bb62b-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="bb62b-106">Las entradas a Oracle $O $ son:</span><span class="sxs-lookup"><span data-stu-id="bb62b-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="bb62b-107">Un entero que indiza la marca qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="bb62b-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="bb62b-108">El registro del sistema $s $ que almacenará el estado de cuanto deseado, $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="bb62b-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="bb62b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bb62b-109">Remarks</span></span>

<span data-ttu-id="bb62b-110">Este Oracle definido por $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ actúa sobre el estado de base de cálculo $ \ket {0} \_ {f} \ket {0} \_ s $ para crear el estado de destino $ \ket{\psi} \_ s $ con amplitud $ \lambda $ en la base marcada por $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="bb62b-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="bb62b-111">El primer parámetro es un índice del registro qubit de $ \ket {0} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="bb62b-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="bb62b-112">El segundo parámetro engloba ambos registros.</span><span class="sxs-lookup"><span data-stu-id="bb62b-112">The second parameter encompassed both registers.</span></span>