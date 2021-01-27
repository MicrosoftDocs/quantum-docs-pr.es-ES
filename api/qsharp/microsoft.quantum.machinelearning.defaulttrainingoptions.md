---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856004"
---
# <a name="defaulttrainingoptions-function"></a>DefaultTrainingOptions función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Devuelve un conjunto predeterminado de opciones para los clasificadores de entrenamiento.

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>Salida: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Un conjunto razonable de opciones de entrenamiento predeterminadas para usar al entrenar clasificadores.

## <a name="example"></a>Ejemplo

Para usar las opciones predeterminadas, pero con medidas adicionales, use el `w/` operador:

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```