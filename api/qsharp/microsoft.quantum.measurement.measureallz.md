---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operación MeasureAllZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854667"
---
# <a name="measureallz-operation"></a>Operación MeasureAllZ

Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mide conjuntamente un registro de qubits en la base de Pauli Z.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Descripción

Mide un registro de qubits en el $Z \otimes Z \otimes \cdots \otimes Z $, que representa la paridad del registro completo.

## <a name="input"></a>Entrada

### <a name="register--qubit"></a>registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

El registro que se va a medir.



## <a name="output--__invalidresult__"></a>Salida: __no <Result> válido__

El resultado de medir $Z \otimes Z \otimes \cdots \otimes Z $.