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
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="97e61-102">Tipo definido por el usuario GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="97e61-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="97e61-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="97e61-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="97e61-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97e61-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97e61-105">Representa una colección de `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="97e61-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="97e61-106">Se recorre en iteración esta colección usando un entero de índice único y se supone que el tamaño de la colección es conocido.</span><span class="sxs-lookup"><span data-stu-id="97e61-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="97e61-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="97e61-107">Remarks</span></span>

<span data-ttu-id="97e61-108">Las instancias de `GeneratorSystem` se pueden definir fácilmente mediante la <xref:microsoft.quantum.arrays.lookupfunction> función.</span><span class="sxs-lookup"><span data-stu-id="97e61-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="97e61-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97e61-109">See Also</span></span>

- [<span data-ttu-id="97e61-110">Microsoft. Quantum. arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="97e61-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)