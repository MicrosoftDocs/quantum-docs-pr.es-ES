---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingFromBEandQubit
title: Operación ApplyBlockEncodingFromBEandQubit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingFromBEandQubit
qsharp.summary: Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding
ms.openlocfilehash: 16d54a982b020f4d4ded5901ec07de44a2d09726
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229620"
---
# <a name="applyblockencodingfrombeandqubit-operation"></a>Operación ApplyBlockEncodingFromBEandQubit

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


La conversión de ((LittleEndian, qubit []) => () es ADJ + CTL) a BlockEncoding

```qsharp
operation ApplyBlockEncodingFromBEandQubit (op : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl), auxiliary : Qubit[], system : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="op--littleendianqubit--unit--is-adj--ctl"></a>OP: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL




### <a name="auxiliary--qubit"></a>auxiliar: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="system--qubit"></a>sistema: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

