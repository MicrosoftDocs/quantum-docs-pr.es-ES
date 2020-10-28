---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728295"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Calcula el tamaño de paso de Trotter en la implementación recursiva del algoritmo de simulación de Trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="order--int"></a>orden: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observaciones

Esta operación usa una Convención de indexación diferente de la de [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). En concreto, `DecomposedIntoTimeStepsCA(_, 4)` se corresponde con el $p escalar _2 (\lambda) $ en Quant-pH/0508139.