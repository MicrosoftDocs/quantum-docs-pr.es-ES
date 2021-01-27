---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operación DrawCategorical
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a9fe1b08e80abc65a5c4b803f0cb8a5e7a62759c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851151"
---
# <a name="drawcategorical-operation"></a>Operación DrawCategorical

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dibuja un ejemplo aleatorio a partir de una distribución de categorías especificada por una lista de probablities.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Descripción

La probabilidad de seleccionar un índice específico es proporcional al valor del elemento de la matriz en dicho índice.
Los elementos de matriz que son iguales a cero se omiten y sus índices nunca se devuelven. Si algún elemento de la matriz es menor que cero, o si ningún elemento de la matriz es mayor que cero, se produce un error en la operación.

## <a name="input"></a>Entrada

### <a name="probs--double"></a>sondeos: [Double](xref:microsoft.quantum.lang-ref.double)[]

Una matriz de números de punto flotante proporcional a la probabilidad de seleccionar cada índice.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Un entero $i $ con probabilidad $ \Pr (i) = p_i/\ sum_i p_i $, donde $p _i $ es el elemento $i $ TH de `probs` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. random. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)