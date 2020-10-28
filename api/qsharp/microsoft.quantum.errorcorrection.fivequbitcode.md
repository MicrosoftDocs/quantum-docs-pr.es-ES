---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727059"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode función)

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


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