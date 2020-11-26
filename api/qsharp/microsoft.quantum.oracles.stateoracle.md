---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Tipo definido por el usuario StateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226611"
---
# <a name="stateoracle-user-defined-type"></a>Tipo definido por el usuario StateOracle

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa una preparación de Oracle para el estado.

Las entradas a Oracle $O $ son:

- Un entero que indiza la marca qubit $f $.
- El registro del sistema $s $ que almacenará el estado de cuanto deseado, $ \ket{\psi} \_ s $.

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Observaciones

Este Oracle definido por $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ actúa sobre el estado de base de cálculo $ \ket {0} \_ {f} \ket {0} \_ s $ para crear el estado de destino $ \ket{\psi} \_ s $ con amplitud $ \lambda $ en la base marcada por $ \ket {1} \_ f $.
El primer parámetro es un índice del registro qubit de $ \ket {0} \_ f $. El segundo parámetro engloba ambos registros.