---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Operación ApplyXControlledOnTruthTable
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: aa4e1bc0d5058228721728a894b896331ec626d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203304"
---
# <a name="applyxcontrolledontruthtable-operation"></a>Operación ApplyXControlledOnTruthTable

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica la @"microsoft.quantum.intrinsic.x" operación en `target` , si la función booleana se `func` evalúa como true para la asignación clásica en `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

La operación implementa la operación unitario \begin{align} U\ket {x} \ les {y} = \ket{x}\ket{y \oplus f (x)} \end{align} donde $x $ y $y $ representan `controlRegister` y `target` , respectivamente.

La función booleana $f $ se representa como una tabla de verdad en términos de un entero grande.
Por ejemplo, la función mayoritario en tres entradas se representa mediante bitstring `11101000` , donde el bit más significativo `1` corresponde a la asignación de entrada `(1, 1, 1)` y el bit menos significativo `0` corresponde a la asignación de entrada `(0, 0, 0)` .
Se puede representar mediante el número entero grande `0xE8L` en notación hexadecimal o como `232L` en notación decimal.  El `L` sufijo indica que la constante es de tipo `BigInt` .
También se pueden encontrar más detalles sobre esta representación en las [tablas reales Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).

La implementación de hace uso de las @"microsoft.quantum.intrinsic.cnot" puertas de y @"microsoft.quantum.intrinsic.r1" .

## <a name="input"></a>Entrada

### <a name="func--bigint"></a>FUNC: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Tabla de verdad booleana representada como Big Integer


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro de qubits de control


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de destino



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencias

- [*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv: Quant-pH/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Dittrich Soeken*, *Martin Roetteler*, arXiv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTableWithCleanTarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)