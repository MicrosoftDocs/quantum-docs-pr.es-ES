---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: Operación ApplyWithCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: abc62791416e78c1b2937a226327b71da8b8e288
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729008"
---
# <a name="applywithca-operation"></a>Operación ApplyWithCA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dadas dos operaciones, se aplica una como conjugada con la otra.

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit
```


## <a name="description"></a>Descripción

Dadas dos operaciones, que se describen respectivamente por los operadores unitarios $U $ y $V $, se aplican en la secuencia $U ^ {\dagger} V U $. Es decir, esta operación implementa el operador unitario proporcionado por $V $ conjugado con $U $.

## <a name="input"></a>Entrada

### <a name="outeroperation--t--unit-adj"></a>outerOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

La operación $U $ que se debe usar para conjugado $V $. Tenga en cuenta que la operación exterior $U $ debe ser adjointable, pero no es necesario que sea controlable.


### <a name="inneroperation--t--unit-adj--ctl"></a>innerOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Operación $V $ que se va a conjugado.


### <a name="target--t"></a>destino: ' t

Entrada que se va a proporcionar a las operaciones externas e internas.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Destino en el que actúa cada una de las operaciones internas y externas.

## <a name="remarks"></a>Observaciones

La operación exterior siempre se supone que es adjointable, pero no es necesario que se pueda controlar para que la operación combinada sea controlable.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Microsoft. Quantum. Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)