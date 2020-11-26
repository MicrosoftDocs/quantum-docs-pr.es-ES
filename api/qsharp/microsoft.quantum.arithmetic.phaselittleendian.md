---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Tipo definido por el usuario PhaseLittleEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222429"
---
# <a name="phaselittleendian-user-defined-type"></a>Tipo definido por el usuario PhaseLittleEndian

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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