---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
title: Tipo definido por el usuario OptimizedBEGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEGeneratorSystem
qsharp.summary: Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.
ms.openlocfilehash: 06d13a8a64a3c572821ec97f8776d6f1dbe4a4ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727743"
---
# <a name="optimizedbegeneratorsystem-user-defined-type"></a><span data-ttu-id="2a795-102">Tipo definido por el usuario OptimizedBEGeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="2a795-102">OptimizedBEGeneratorSystem user defined type</span></span>

<span data-ttu-id="2a795-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2a795-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2a795-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a795-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a795-105">Función que devuelve `OptimizedBETermIndex` datos para `n` el término dado un entero `n` , junto con el número de términos de la primera `Int` y la suma de los valores absolutos de todos los coeficientes de los términos de `Double` .</span><span class="sxs-lookup"><span data-stu-id="2a795-105">Function that returns `OptimizedBETermIndex` data for term `n` given an integer `n`, together with the number of terms in the first `Int` and the sum of absolute-values of all term coefficients in the `Double`.</span></span>

```qsharp

newtype OptimizedBEGeneratorSystem = (Int, Double, (Int -> Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex));
```

