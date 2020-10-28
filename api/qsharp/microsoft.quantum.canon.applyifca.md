---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: Operación ApplyIfCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: 9057c79622f15a082963d94fc261664e00322feb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729589"
---
# <a name="applyifca-operation"></a>Operación ApplyIfCA

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica una operación de unitario condicionada en un bit clásico.

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>Descripción

Dada una operación `op` y un valor de bit `bit` , se aplica `op` a `target` si `bit` es `true` . Si es `false` , no sucede nada con `target` .
El sufijo `CA` indica que la operación que se va a aplicar es la unitario (controlable y adjointable).

## <a name="input"></a>Entrada

### <a name="op--t--unit-ctl--adj"></a>OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ

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