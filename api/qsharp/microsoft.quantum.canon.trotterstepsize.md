---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840074"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Calcula el tamaño de paso de Trotter en la implementación recursiva del algoritmo de simulación de Trotter.

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>Entrada

### <a name="order--int"></a>orden: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Observaciones

Esta operación usa una Convención de indexación diferente de la de [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139). En concreto, `DecomposedIntoTimeStepsCA(_, 4)` se corresponde con el $p escalar _2 (\lambda) $ en Quant-pH/0508139.