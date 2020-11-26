---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Operación ApplyWithInputTransformation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3586e9a114a550fb1989186e9c18fe4f344cf060
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217193"
---
# <a name="applywithinputtransformation-operation"></a>Operación ApplyWithInputTransformation

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una operación que acepta alguna entrada, una función que devuelve una salida compatible con esa operación y una entrada a esa función, aplica la operación utilizando la función para transformar la entrada a un formato esperado por la operación.

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a>Entrada

### <a name="fn--u---t"></a>FN: ' U-> ' t

Función que transforma la entrada especificada en un formato esperado por la operación.


### <a name="op--t--unit"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> 

Operación que se va a aplicar.


### <a name="input--u"></a>entrada: ' U

Una entrada a la función.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada


### <a name="u"></a>' U



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyWithInputTransformationA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationC](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationCA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)