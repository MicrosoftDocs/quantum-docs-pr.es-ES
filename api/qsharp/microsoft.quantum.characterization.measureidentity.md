---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operación MeasureIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728186"
---
# <a name="measureidentity-operation"></a>Operación MeasureIdentity

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Configura [](https://nuget.org/packages/)


Mide el operador de identidad en un registro de qubits.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Entrada

### <a name="register--qubit"></a>registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

El registro que se va a medir.



## <a name="output--__invalidresult__"></a>Salida: __no <Result> válido__

Valor del resultado `Zero` .

## <a name="remarks"></a>Observaciones

Dado que $ \boldone $ solo tiene eigenvalue $1 $ y no tiene un eigenvalue negativo, esta operación siempre devuelve `Zero` , correspondiente a eigenvalue $ + 1 = (-1) ^ 0 $, y no produce una contracción del estado de `register` .

Por su cuenta, esta operación no es útil, pero es útil en el contexto del proceso Tomography, ya que proporciona información sobre la preservación del seguimiento de un proceso Quantum.
En concreto, una máquina de destino con medición de pérdida debe reemplazar esta operación por una medida real de $ \boldone $.