---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732812"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


Devuelve el número de qubits necesarios para codificar un vector de característica determinado.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Entrada

### <a name="sample--double"></a>ejemplo: [Double](xref:microsoft.quantum.lang-ref.double)[]

Un vector de característica de ejemplo que se va a codificar en un registro qubit.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Tamaño necesario para codificar `sample` en un registro qubit, expresado como un número de qubits.