---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 9b8861a4112c4e6c9db994339353c771a3de81a6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229994"
---
# <a name="purifiedmixedstaterequirements-function"></a>PurifiedMixedStateRequirements función)

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve el número total de qubits que deben asignarse para aplicar la operación devuelta por @"microsoft.quantum.preparation.purifiedmixedstate" .

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

El error de destino $ \epsilon $.


### <a name="ncoefficients--int"></a>nCoefficients: [int](xref:microsoft.quantum.lang-ref.int)

El número de coeficientes que se van a especificar en la preparación de un estado mixto.



## <a name="output--mixedstatepreparationrequirements"></a>Salida: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

Una descripción de cuántos qubits son necesarias en total y para cada uno de los registros de índice y de elementos no utilizados usados por la @"microsoft.quantum.preparation.purifiedmixedstate" función.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. preparación. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)