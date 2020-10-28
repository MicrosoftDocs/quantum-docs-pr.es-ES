---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definido por el usuario GeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733540"
---
# <a name="generatorsystem-user-defined-type"></a>Tipo definido por el usuario GeneratorSystem

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Configura [](https://nuget.org/packages/)


Representa una colección de `GeneratorIndex` es.

Se recorre en iteración esta colección usando un entero de índice único y se supone que el tamaño de la colección es conocido.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Observaciones

Las instancias de `GeneratorSystem` se pueden definir fácilmente mediante la <xref:microsoft.quantum.arrays.lookupfunction> función.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)