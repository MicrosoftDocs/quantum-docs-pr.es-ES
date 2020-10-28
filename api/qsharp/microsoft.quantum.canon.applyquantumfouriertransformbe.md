---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Operación ApplyQuantumFourierTransformBE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729393"
---
# <a name="applyquantumfouriertransformbe-operation"></a>Operación ApplyQuantumFourierTransformBE

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Realiza la transformación de Fourier de Quantum en un registro de Quantum que contiene un entero en la representación Big-Endian.

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="qs--bigendian"></a>q: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registro Quantum al que se aplica la transformación Fourier de Quantum



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Se supone que la entrada y la salida están en big endian codificación.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApproximateQFT](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [Microsoft. Quantum. Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)