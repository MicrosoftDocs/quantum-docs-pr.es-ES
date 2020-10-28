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
# <a name="deterministicstateoracle-user-defined-type"></a>Tipo definido por el usuario DeterministicStateOracle

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Configura [](https://nuget.org/packages/)


Representa una preparación de Oracle para el estado determinista.

La entrada a Oracle $O $ es:

- El registro que almacenará el estado de cuanto deseado, $ \ket{\psi} \_ s $.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Observaciones

Este Oracle definido por $O \ket {0} = \ket{\psi} $ actúa en el estado de base de cálculo $ \ket {0} $ para crear el estado $ \ket{\psi} $.
El primer parámetro es el registro qubit de $ \ket{\psi} $.