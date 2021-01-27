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
# <a name="deterministicstateoracle-user-defined-type"></a>Tipo definido por el usuario DeterministicStateOracle

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa una preparación de Oracle para el estado determinista.

La entrada a Oracle $O $ es:

- El registro que almacenará el estado de cuanto deseado, $ \ket{\psi} \_ s $.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Observaciones

Este Oracle definido por $O \ket {0} = \ket{\psi} $ actúa en el estado de base de cálculo $ \ket {0} $ para crear el estado $ \ket{\psi} $.
El primer parámetro es el registro qubit de $ \ket{\psi} $.