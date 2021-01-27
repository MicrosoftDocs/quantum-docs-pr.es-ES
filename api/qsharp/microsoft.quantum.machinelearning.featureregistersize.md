---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848440"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devuelve el número de qubits necesarios para codificar un vector de característica determinado.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Entrada

### <a name="sample--double"></a>ejemplo: [Double](xref:microsoft.quantum.lang-ref.double)[]

Un vector de característica de ejemplo que se va a codificar en un registro qubit.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Tamaño necesario para codificar `sample` en un registro qubit, expresado como un número de qubits.