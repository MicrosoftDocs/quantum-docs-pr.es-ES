---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definido por el usuario UnivariateOptimizationResult
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854564"
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