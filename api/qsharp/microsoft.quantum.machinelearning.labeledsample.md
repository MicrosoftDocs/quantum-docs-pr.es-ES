---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido por el usuario LabeledSample
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196334"
---
# <a name="labeledsample-user-defined-type"></a>Tipo definido por el usuario LabeledSample

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Un ejemplo, etiquetado con una clase a la que pertenece el ejemplo.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="features--double"></a>Características: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vector de características para el ejemplo especificado.
### <a name="label--int"></a>Etiqueta: [int](xref:microsoft.quantum.lang-ref.int)

Una etiqueta de entero para la clase a la que pertenece este ejemplo.