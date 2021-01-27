---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856828"
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