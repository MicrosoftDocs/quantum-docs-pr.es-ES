---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definido por el usuario GeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858419"
---
# <a name="generatorsystem-user-defined-type"></a>Tipo definido por el usuario GeneratorSystem

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa una colección de `GeneratorIndex` es.

Se recorre en iteración esta colección usando un entero de índice único y se supone que el tamaño de la colección es conocido.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Observaciones

Las instancias de `GeneratorSystem` se pueden definir fácilmente mediante la <xref:microsoft.quantum.arrays.lookupfunction> función.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)