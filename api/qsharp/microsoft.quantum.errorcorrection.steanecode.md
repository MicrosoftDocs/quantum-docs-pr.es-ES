---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853053"
---
# <a name="steanecode-function"></a>SteaneCode función)

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve un valor de CSS que representa el codificador y descodificador de código ⟦ 7, 1, 3 ⟧ Steane con medición de síndrome en contexto.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Salida: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Objeto de tipo CSS que recopila todos los datos pertinentes para realizar la codificación y la corrección de errores para el código Steane de ⟦ 7, 1, 3 ⟧.

## <a name="remarks"></a>Observaciones

Este código se encontró en el siguiente documento:

- A. Steane, "interferencia de varias partículas y corrección de errores de Quantum", proc. Roy. SOC. Lond. A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.