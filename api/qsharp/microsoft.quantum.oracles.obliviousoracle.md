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
# <a name="obliviousoracle-user-defined-type"></a>Tipo definido por el usuario ObliviousOracle

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa una amplificación de amplitud de Oracle para desconocen.

Las entradas a Oracle $O $ son:

- El registro ancilla $a $ en el que $O $ actúa.
- El registro del sistema $s $ en el que se aplica el unitario $U $ deseado, después seleccionado en Register $a $ en State $ \ket{t} \_ a $.

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Observaciones

Este Oracle definido por $ $ O\ket {s} \_ a\ket {\ PSI} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ actúa en el estado ancilla $ \ket{s} $ \_ para implementar la unidad unitario $U $ en cualquier estado del sistema $ \ket{\psi} \_ s $ con amplitud $ \lambda $ en la base marcada por $ \ket{t} \_ a $.
El primer parámetro es el registro qubit de $ \ket{s} \_ a $. El segundo parámetro es el registro qubit de $ \ket{\psi} \_ s $.