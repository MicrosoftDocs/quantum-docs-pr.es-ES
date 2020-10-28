---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: Operación ApplyIfA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 279a069176ee24ed83406f72170462bf58c790d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729604"
---
# <a name="applyifa-operation"></a>Operación ApplyIfA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación adjointable condicionada en un bit clásico.

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>Descripción

Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` . Si es `false` , no sucede nada con `target` .
El sufijo `A` indica que la operación que se va a aplicar es adjointable.

## <a name="input"></a>Entrada

### <a name="op--t--unit-adj"></a>OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)

Operación que se va a aplicar condicionalmente.


### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

un valor booleano que controla si se aplica o no la operación.


### <a name="target--t"></a>destino: ' t

Entrada a la que se aplica la operación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo de entrada de la operación que se va a aplicar condicionalmente.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. Quantum. Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. Quantum. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)