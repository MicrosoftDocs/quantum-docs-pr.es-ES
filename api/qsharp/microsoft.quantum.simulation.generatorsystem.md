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
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="1f487-102">Tipo definido por el usuario GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="1f487-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="1f487-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1f487-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1f487-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f487-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f487-105">Representa una colección de `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="1f487-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="1f487-106">Se recorre en iteración esta colección usando un entero de índice único y se supone que el tamaño de la colección es conocido.</span><span class="sxs-lookup"><span data-stu-id="1f487-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="1f487-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1f487-107">Remarks</span></span>

<span data-ttu-id="1f487-108">Las instancias de `GeneratorSystem` se pueden definir fácilmente mediante la <xref:microsoft.quantum.arrays.lookupfunction> función.</span><span class="sxs-lookup"><span data-stu-id="1f487-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f487-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f487-109">See Also</span></span>

- [<span data-ttu-id="1f487-110">Microsoft. Quantum. arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="1f487-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)