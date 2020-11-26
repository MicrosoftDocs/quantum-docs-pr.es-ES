---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: Tipo definido por el usuario SequentialModel
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196181"
---
# <a name="sequentialmodel-user-defined-type"></a>Tipo definido por el usuario SequentialModel

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Describe un modelo de clasificador de Quantum compuesto por una secuencia de giros con parámetros y controlados, una asignación de ángulos de rotación y una diferencia entre las dos clases reconocidas por el modelo.

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="structure--controlledrotation"></a>Estructura: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Secuencia de las rotaciones controladas utilizadas para clasificar las entradas.
### <a name="parameters--double"></a>Parámetros: [Double](xref:microsoft.quantum.lang-ref.double)[]

Asignación de ángulos de rotación a la estructura de clasificación indicada.
### <a name="bias--double"></a>Bias: [Double](xref:microsoft.quantum.lang-ref.double)

La diferencia entre las dos clases reconocidas por este clasificador.

## <a name="references"></a>Referencias

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)