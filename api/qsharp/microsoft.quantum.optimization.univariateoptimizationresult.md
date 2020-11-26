---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definido por el usuario UnivariateOptimizationResult
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194039"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>Tipo definido por el usuario UnivariateOptimizationResult

Espacio de nombres: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa el resultado de la optimización de una función univariante.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="coordinate--double"></a>Coordenada: [Double](xref:microsoft.quantum.lang-ref.double)

Entrada en la que se encontró un óptimo.
### <a name="value--double"></a>Valor: [Double](xref:microsoft.quantum.lang-ref.double)

Valor devuelto por la función de forma óptima.