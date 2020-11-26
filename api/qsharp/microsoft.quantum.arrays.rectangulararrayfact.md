---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220423"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact función)

Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa una condición que una matriz bidimensional tiene una forma rectangular

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Descripción

Esta función garantiza que cada fila de una matriz tiene la misma longitud.

## <a name="input"></a>Entrada

### <a name="array--t"></a>matriz: ' t [] []

Matriz bidimensional de elementos.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Un mensaje que se va a imprimir si la matriz no es una matriz rectangular



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de cada elemento de `array` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. arrays. SquareArrayFact](xref:Microsoft.Quantum.Arrays.SquareArrayFact)