---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200890"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode función)

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve un valor de QECC que representa el codificador y descodificador de código ⟦ 5, 1, 3 ⟧ con una medida de síndrome en contexto.

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>Salida: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Devuelve una implementación de un código de corrección de errores de Quantum especificando un `QECC` tipo.

## <a name="remarks"></a>Observaciones

Este código se encontró de forma independiente en los dos documentos siguientes:

- C. H. Bennett, D. DiVincenzo, J. A. Smolin y W. K. Wootters, "mezclado de estado mixto y corrección de errores de Quantum", "físico. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 y
- R. Laflamme, C. Miquel, J. P. Paz y W. H. Zurek, "código de corrección de errores de Quantum perfectos", "físico. Rev. paleta. 77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019