---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms
title: Tipo definido por el usuario JWOptimizedHTerms
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JWOptimizedHTerms
qsharp.summary: Format of data passed from C# to Q# to represent terms of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: d75737f23db84f2a21daff7a0ebcb8ae51feb642
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727755"
---
# <a name="jwoptimizedhterms-user-defined-type"></a><span data-ttu-id="ad7e0-102">Tipo definido por el usuario JWOptimizedHTerms</span><span class="sxs-lookup"><span data-stu-id="ad7e0-102">JWOptimizedHTerms user defined type</span></span>

<span data-ttu-id="ad7e0-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ad7e0-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ad7e0-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad7e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad7e0-105">Formato de los datos pasados de C# a Q # para representar los términos del Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="ad7e0-105">Format of data passed from C# to Q# to represent terms of the Hamiltonian.</span></span>
<span data-ttu-id="ad7e0-106">El significado de los datos representados viene determinado por el algoritmo que lo recibe.</span><span class="sxs-lookup"><span data-stu-id="ad7e0-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JWOptimizedHTerms = (Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[]);
```

