---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Tipo definido por el usuario ObliviousOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842560"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="756e9-102">Tipo definido por el usuario ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="756e9-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="756e9-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="756e9-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="756e9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="756e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="756e9-105">Representa una amplificación de amplitud de Oracle para desconocen.</span><span class="sxs-lookup"><span data-stu-id="756e9-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="756e9-106">Las entradas a Oracle $O $ son:</span><span class="sxs-lookup"><span data-stu-id="756e9-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="756e9-107">El registro ancilla $a $ en el que $O $ actúa.</span><span class="sxs-lookup"><span data-stu-id="756e9-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="756e9-108">El registro del sistema $s $ en el que se aplica el unitario $U $ deseado, después seleccionado en Register $a $ en State $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="756e9-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="756e9-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="756e9-109">Remarks</span></span>

<span data-ttu-id="756e9-110">Este Oracle definido por $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ actúa en el estado ancilla $ \ket{s} $ \_ para implementar la unidad unitario $U $ en cualquier estado del sistema $ \ket{\psi} \_ s $ con amplitud $ \lambda $ en la base marcada por $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="756e9-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="756e9-111">El primer parámetro es el registro qubit de $ \ket{s} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="756e9-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="756e9-112">El segundo parámetro es el registro qubit de $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="756e9-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>