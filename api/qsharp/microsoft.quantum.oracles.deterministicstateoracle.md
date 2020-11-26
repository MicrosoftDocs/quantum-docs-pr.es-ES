---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: Tipo definido por el usuario DeterministicStateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193937"
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