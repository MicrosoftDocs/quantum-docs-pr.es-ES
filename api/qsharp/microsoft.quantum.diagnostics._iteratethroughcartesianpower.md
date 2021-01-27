---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower operación
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: a27302be75ee701b0629310700b56d222aaef7db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853576"
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

