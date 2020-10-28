---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Tipo definido por el usuario SyndromeMeasOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726963"
---
# <a name="syndromemeasop-user-defined-type"></a>Tipo definido por el usuario SyndromeMeasOp

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


Representa una operación que se utiliza para medir el síndrome de un bloque de código de corrección de errores.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Observaciones

La firma `(LogicalRegister => Syndrome)` representa una operación que actúa conjuntamente en el qubits en `LogicalRegister` y algunos qubits auxiliares seguidos de una medida de la qubits auxiliar para extraer un `Syndrome` valor que representa el `Result[]` de estas medidas.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)