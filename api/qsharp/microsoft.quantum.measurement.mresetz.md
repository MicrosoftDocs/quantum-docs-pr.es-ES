---
uid: Microsoft.Quantum.Measurement.MResetZ
title: Operación MResetZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726507"
---
# <a name="mresetz-operation"></a>Operación MResetZ

Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Configura [](https://nuget.org/packages/)


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