---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: Operación CopyMostSignificantBit
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223296"
---
# <a name="copymostsignificantbit-operation"></a>Operación CopyMostSignificantBit

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Copia el bit más significativo de un registro qubit `from` que representa un entero sin signo en el qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="from--littleendian"></a>de: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Entero sin signo del que se copia el bit más alto.
el entero se codifica en formato Little-Endian.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit en la que se va a copiar el bit más alto. La codificación de bits se basa en el cálculo.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. aritmético. LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)