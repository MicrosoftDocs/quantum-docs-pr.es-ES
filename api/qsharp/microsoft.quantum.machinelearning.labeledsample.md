---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: Tipo definido por el usuario LabeledSample
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726627"
---
# <a name="labeledsample-user-defined-type"></a>Tipo definido por el usuario LabeledSample

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


Un ejemplo, etiquetado con una clase a la que pertenece el ejemplo.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="features--double"></a>Características: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vector de características para el ejemplo especificado.
### <a name="label--int"></a>Etiqueta: [int](xref:microsoft.quantum.lang-ref.int)

Una etiqueta de entero para la clase a la que pertenece este ejemplo.