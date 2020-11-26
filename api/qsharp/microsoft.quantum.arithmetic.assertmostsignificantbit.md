---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operación AssertMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223789"
---
# <a name="assertmostsignificantbit-operation"></a>Operación AssertMostSignificantBit

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Valida que el valor de qubit más importante de un registro qubit que representa un entero sin signo está en un estado determinado.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="value--__invalidresult__"></a>valor: __no <Result> válido__

Valor del bit más alto que se va a validar.


### <a name="number--littleendian"></a>número: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Entero sin signo del que se comprueba el bit más alto.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

La versión controlada de esta operación omite los controles.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Intrinsic. Assert](xref:Microsoft.Quantum.Intrinsic.Assert)