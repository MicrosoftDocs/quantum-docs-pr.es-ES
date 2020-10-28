---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definido por el usuario UnivariateOptimizationResult
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733404"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>Tipo definido por el usuario UnivariateOptimizationResult

Espacio de nombres: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Configura [](https://nuget.org/packages/)


Representa el resultado de la optimización de una función univariante.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="coordinate--double"></a>Coordenada: [Double](xref:microsoft.quantum.lang-ref.double)

Entrada en la que se encontró un óptimo.
### <a name="value--double"></a>Valor: [Double](xref:microsoft.quantum.lang-ref.double)

Valor devuelto por la función de forma óptima.