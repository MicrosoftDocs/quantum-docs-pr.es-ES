---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: Tipo definido por el usuario ValidationResults
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846088"
---
# <a name="validationresults-user-defined-type"></a>Tipo definido por el usuario ValidationResults

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paquete: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Los resultados de haber validado un clasificador con un conjunto de ejemplos.

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="nmisclassifications--int"></a>NMisclassifications: [int](xref:microsoft.quantum.lang-ref.int)

El número de clasificaciones incorrectas observadas durante la validación.
### <a name="nvalidationsamples--int"></a>NValidationSamples: [int](xref:microsoft.quantum.lang-ref.int)

