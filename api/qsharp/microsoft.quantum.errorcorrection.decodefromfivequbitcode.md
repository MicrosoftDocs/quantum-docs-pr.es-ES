---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Operación DecodeFromFiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 9b4580cb88f03a16e3c9c55511d0ec5968cc636f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853165"
---
# <a name="decodefromfivequbitcode-operation"></a>Operación DecodeFromFiveQubitCode

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Descodifica el código Quantum de ⟦ 5, 1, 3 ⟧.

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Entrada

### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Una matriz de qubits que representa el estado lógico de código 5-qubit codificado.



## <a name="output--qubitqubit"></a>Salida: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Matriz qubit de longitud 1 que representa el estado sin codificar en el primer parámetro, junto con el qubits auxiliar en el segundo parámetro.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. ErrorCorrection. FiveQubitCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)