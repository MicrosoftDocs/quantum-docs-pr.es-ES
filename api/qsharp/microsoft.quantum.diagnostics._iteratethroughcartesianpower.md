---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower operación
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: cde25eb99c9e1bde080c5356ecabd9f12cde9bba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213725"
---
# <a name="_iteratethroughcartesianpower-operation"></a>_iterateThroughCartesianPower operación

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Recorre en iteración una variable a través de un producto cartesiano [0, Bounds [0]-1] × [0, Bounds [1]-1] × [0, Bounds [length (Bounds)-1]-1] y calls OP (arr) para cada elemento del producto cartesiano

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>Entrada

### <a name="length--int"></a>longitud: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>valor: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>OP: [int](xref:microsoft.quantum.lang-ref.int)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)> 





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

