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
# <a name="stateoracle-user-defined-type"></a>Tipo definido por el usuario StateOracle

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Configura [](https://nuget.org/packages/)


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