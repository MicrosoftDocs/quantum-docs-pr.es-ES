---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: Operación AssertMostSignificantBit
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843419"
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