---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operación MeasureInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222650"
---
# <a name="measureinteger-operation"></a>Operación MeasureInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mide el contenido de un registro de Quantum y lo convierte en un entero. La medida se realiza con respecto a la base de cálculo estándar, es decir, el eigenbasis de `PauliZ` .

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>Entrada

### <a name="target--littleendian"></a>destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Un registro de Quantum en la codificación Little-Endian.



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)

Entero sin signo que contiene el valor medido de `target` .

## <a name="remarks"></a>Observaciones

Esta operación restablece su registro de entrada en el estado $ \ket{00\cdots 0} $, adecuado para volver a la máquina de destino.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)