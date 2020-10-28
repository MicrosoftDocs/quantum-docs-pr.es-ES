---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operación QFTLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728474"
---
# <a name="qftle-operation"></a>Operación QFTLE

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Realiza la transformación de Fourier de Quantum en un registro de Quantum que contiene un entero en la representación Little-Endian.

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="qs--littleendian"></a>q: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registro Quantum al que se aplica la transformación Fourier de Quantum



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Se supone que la entrada y la salida están en little endian codificación.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)