---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operación MaybeChooseElement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192866"
---
# <a name="maybechooseelement-operation"></a>Operación MaybeChooseElement

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dada una matriz de datos y una distribución a través de sus índices, intenta elegir un elemento de forma aleatoria.

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>Entrada

### <a name="data--t"></a>datos: ' t []

Matriz de la que se debe elegir un elemento.


### <a name="indexdistribution--discretedistribution"></a>indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Una distribución a través de los índices de `data` .



## <a name="output--boolt"></a>Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

