---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido por el usuario LabeledSample
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846974"
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