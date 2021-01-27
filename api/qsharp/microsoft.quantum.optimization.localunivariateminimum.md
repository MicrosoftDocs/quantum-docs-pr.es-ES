---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854604"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum función)

Espacio de nombres: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve el mínimo local para una función univariante sobre un intervalo delimitado, mediante una búsqueda de intervalo de Golden.

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>Entrada

### <a name="fn--double---double"></a>FN: [doble](xref:microsoft.quantum.lang-ref.double) -> [doble](xref:microsoft.quantum.lang-ref.double)

La función univariante que se va a minimizar.


### <a name="bounds--doubledouble"></a>Bounds: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))

El intervalo en el que se debe encontrar el mínimo local.


### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Precisión en la entrada de la función que se va a tolerar.
La búsqueda del local optima continuará hasta que el intervalo tenga un ancho inferior al de esta tolerancia.



## <a name="output--univariateoptimizationresult"></a>Salida: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

Un local optima de la función especificada, que se encuentra dentro de los límites especificados.