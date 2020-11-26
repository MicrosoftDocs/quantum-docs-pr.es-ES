---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Operación ApplyOuterCDKMAdder
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 81311a75beedb62331184faf4e1523f3ccc74f43
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190673"
---
# <a name="applyoutercdkmadder-operation"></a>Operación ApplyOuterCDKMAdder

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Operación de transporte de rizo reversible y en contexto que se usa en la operación de suma de enteros RippleCarryAdderCDKM a continuación.
Dados dos registros de qubit `xs` y `ys` de la misma longitud, la operación aplica una secuencia de transporte de rizo de CNOT y puertas de CCNOT con qubits en `xs` y `ys` como los controles y Qubits `xs` como destinos.

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Primer registro de qubit, que contiene controles y destinos.


### <a name="ys--littleendian"></a>calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Segundo registro de qubit, que contribuye a los controles.


### <a name="ancilla--qubit"></a>ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ancilla qubit usado en RippleCarryAdderCDKM pasado a esta operación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencias

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "un nuevo circuito de adición del transporte de onda de Quantum", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1