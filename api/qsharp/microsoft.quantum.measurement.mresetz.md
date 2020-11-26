---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operación MResetZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194141"
---
# <a name="mresetz-operation"></a>Operación MResetZ

Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Mide un único qubit en la Z y lo restablece a un estado inicial fijo después de la medición.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Descripción

Realiza una medición de un solo qubit en el $Z $-Basis y garantiza que el qubit se devuelve a $ \ket {0} $ después de la medida.

## <a name="input"></a>Entrada

### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Un único qubit que se va a medir.



## <a name="output--__invalidresult__"></a>Salida: __no <Result> válido__

El resultado de medir `target` en Pauli $Z $.