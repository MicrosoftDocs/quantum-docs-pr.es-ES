---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845499"
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

## <a name="example"></a>Ejemplo

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. arrays. SquareArrayFact](xref:Microsoft.Quantum.Arrays.SquareArrayFact)