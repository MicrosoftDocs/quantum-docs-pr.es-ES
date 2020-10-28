---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Operación EncodeIntoSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727082"
---
# <a name="encodeintosteanecode-operation"></a>Operación EncodeIntoSteaneCode

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Configura [](https://nuget.org/packages/)


Una operación de codificación que asigna un registro de Quantum sin codificar a un registro de Quantum codificado en el Código ⟦ 7, 1, 3 ⟧ Steane Quantum.

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Entrada

### <a name="physregister--qubit"></a>physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro qubit que contiene el estado de Quantum sin codificar


### <a name="auxqubits--qubit"></a>auxQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro qubit que es inicialmente cero y que se agrega al sistema Quantum para que se pueda realizar una operación de codificación.



## <a name="output--logicalregister"></a>Salida: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Un registro de Quantum que contiene el estado después de haber aplicado el codificador Steane

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)