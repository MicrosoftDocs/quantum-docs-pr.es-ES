---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856175"
---
# <a name="approximateinputencoder-function"></a>ApproximateInputEncoder función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Dado un conjunto de coeficientes y una tolerancia, devuelve una operación de preparación del estado que prepara cada coeficiente como la amplitud correspondiente del estado de la base de cálculo, hasta la tolerancia especificada.

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia de aproximación que se va a usar para codificar los coeficientes dados en un estado de entrada.


### <a name="coefficients--double"></a>coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]

Los coeficientes que se van a codificar en un estado de entrada.



## <a name="output--stategenerator"></a>Salida: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Operación de preparación de estado que prepara los coeficientes determinados como un estado de entrada en un registro determinado.