---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Tipo definido por el usuario ObliviousOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 7c5b35984f3c8828a5ba9bdae8f9effbc1d378f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726482"
---
# <a name="obliviousoracle-user-defined-type"></a>Tipo definido por el usuario ObliviousOracle

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Configura [](https://nuget.org/packages/)


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