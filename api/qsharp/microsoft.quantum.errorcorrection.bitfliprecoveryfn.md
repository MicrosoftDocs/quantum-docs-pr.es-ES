---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727125"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn función)

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


Función para las operaciones de Pauli de recuperación de la medición de síndrome determinada por búsqueda de tabla para el código de volteo de bits ⟦ de 3, 1, 1 ⟧.

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Salida: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Función de tipo `RecoveryFn` que toma una medición del síndrome `Result[]` y devuelve las `Pauli[]` operaciones que corrigen el error detectado.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)