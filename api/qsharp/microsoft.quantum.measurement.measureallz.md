---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: Operación MeasureAllZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726518"
---
# <a name="measureallz-operation"></a>Operación MeasureAllZ

Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Configura [](https://nuget.org/packages/)


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