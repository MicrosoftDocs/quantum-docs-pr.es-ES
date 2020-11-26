---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operación MultiplyAndAddPhaseByModularInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223874"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>Operación MultiplyAndAddPhaseByModularInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Lo mismo que MultiplyAndAddByModularInteger, pero supone que sumando codifica enteros en QFT.

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Entero $a $ que se va a agregar a cada etiqueta de estado de base.


### <a name="modulus--int"></a>módulo: [int](xref:microsoft.quantum.lang-ref.int)

El módulo $N $ que se toma la suma y la multiplicación con respecto a.


### <a name="multiplier--littleendian"></a>multiplicador: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Un registro de Quantum que representa un entero sin signo cuyo valor se va a agregar a cada etiqueta de estado de base de `summand` .


### <a name="phasesummand--phaselittleendian"></a>phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Un registro de Quantum que representa un entero sin signo que se va a usar como destino para esta operación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Supone que `phaseSummand` tiene el bit más alto establecido en 0.
También se supone que el valor de `phaseSummand` es menor que $N $.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. aritmético. MultiplyAndAddByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)