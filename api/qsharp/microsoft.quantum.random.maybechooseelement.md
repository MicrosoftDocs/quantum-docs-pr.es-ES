---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operación MaybeChooseElement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732172"
---
# <a name="maybechooseelement-operation"></a>Operación MaybeChooseElement

Espacio de nombres: [Microsoft. Quantum. RANDOM](xref:Microsoft.Quantum.Random)

Configura [](https://nuget.org/packages/)


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

