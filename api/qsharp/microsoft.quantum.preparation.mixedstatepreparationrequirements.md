---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: Tipo definido por el usuario MixedStatePreparationRequirements
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: df57b7b43fc84f7ddf68392f6a2b7013225da730
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856930"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a>Tipo definido por el usuario MixedStatePreparationRequirements

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa el número de qubits necesarios para preparar un estado mixto determinado.

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a>Elementos con nombre

### <a name="ntotalqubits--int"></a>NTotalQubits: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="nindexqubits--int"></a>NIndexQubits: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="ngarbagequbits--int"></a>NGarbageQubits: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. PurifiedMixedState](xref:Microsoft.Quantum.PurifiedMixedState)