---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Tipo definido por el usuario PhaseLittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730589"
---
# <a name="phaselittleendian-user-defined-type"></a>Tipo definido por el usuario PhaseLittleEndian

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Configura [](https://nuget.org/packages/)


Enteros sin signo Little-endian en la base de QFT.

Por ejemplo, si $ \ket{x} $ es la codificación Little-Endian del entero $x $ en la base de cálculo, $ \operatorname{QFTLE} \ket{x} $ es la codificación de $x $ en la base de QFT.

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Observaciones

Lo abreviamos `PhaseLittleEndian` como `PhaseLE` en la documentación de.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Microsoft. Quantum. Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)