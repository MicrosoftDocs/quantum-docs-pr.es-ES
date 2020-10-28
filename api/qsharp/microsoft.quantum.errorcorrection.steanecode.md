---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726992"
---
# <a name="steanecode-function"></a>SteaneCode función)

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


Devuelve un valor de CSS que representa el codificador y descodificador de código ⟦ 7, 1, 3 ⟧ Steane con medición de síndrome en contexto.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Salida: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Objeto de tipo CSS que recopila todos los datos pertinentes para realizar la codificación y la corrección de errores para el código Steane de ⟦ 7, 1, 3 ⟧.

## <a name="remarks"></a>Observaciones

Este código se encontró en el siguiente documento:

- A. Steane, "interferencia de varias partículas y corrección de errores de Quantum", proc. Roy. SOC. Lond. A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.