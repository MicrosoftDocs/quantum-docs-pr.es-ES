---
uid: Microsoft.Quantum.Canon.QFT
title: Operación QFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852292"
---
# <a name="qft-operation"></a>Operación QFT

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza la transformación de Fourier de Quantum en un registro de Quantum que contiene un entero en la representación Big-Endian.

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="qs--bigendian"></a>q: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registro Quantum al que se aplica la transformación Fourier de Quantum



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Se supone que la entrada y la salida están en big endian codificación.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)