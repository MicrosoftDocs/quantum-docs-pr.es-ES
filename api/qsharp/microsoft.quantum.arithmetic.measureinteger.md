---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operación MeasureInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843118"
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