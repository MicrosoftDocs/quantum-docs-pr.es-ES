---
uid: Microsoft.Quantum.Measurement.MResetX
title: Operación MResetX
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 44459e681daf1d28ce7d45f91ad59059babe5716
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853755"
---
# <a name="mresetx-operation"></a>Operación MResetX

Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Mide un único qubit en X y lo restablece a un estado inicial fijo después de la medición.

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a>Descripción

Realiza una medición de un solo qubit en el $X $-Basis y garantiza que el qubit se devuelve a $ \ket {0} $ después de la medida.

## <a name="input"></a>Entrada

### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Un único qubit que se va a medir.



## <a name="output--__invalidresult__"></a>Salida: __no <Result> válido__

El resultado de medir `target` en Pauli $X $.