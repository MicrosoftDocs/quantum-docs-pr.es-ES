---
uid: Microsoft.Quantum.Canon.ApplyWithC
title: Operación ApplyWithC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithC
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: 8de1ddf0bf176853b33926be7647bc5d1d35095d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729014"
---
# <a name="applywithc-operation"></a>Operación ApplyWithC

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Dadas dos operaciones, se aplica una como conjugada con la otra.

```qsharp
operation ApplyWithC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl), target : 'T) : Unit
```


## <a name="description"></a>Descripción

Dadas dos operaciones, que se describen respectivamente por los operadores unitarios $U $ y $V $, se aplican en la secuencia $U ^ {\dagger} V U $. Es decir, esta operación implementa el operador unitario proporcionado por $V $ conjugado con $U $.

## <a name="input"></a>Entrada

### <a name="outeroperation--t--unit-adj"></a>outerOperation: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

La operación $U $ que se debe usar para conjugado $V $. Tenga en cuenta que la operación exterior $U $ debe ser adjointable, pero no es necesario que sea controlable.


### <a name="inneroperation--t--unit-ctl"></a>innerOperation: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)

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
- [Microsoft. Quantum. Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)