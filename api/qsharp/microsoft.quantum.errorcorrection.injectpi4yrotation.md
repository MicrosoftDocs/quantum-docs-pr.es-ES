---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operación InjectPi4YRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825939"
---
# <a name="injectpi4yrotation-operation"></a>Operación InjectPi4YRotation

Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Gira un qubit único por π/4 sobre el eje Y.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a>Descripción

Realiza una rotación de π/4 acerca de `Y` .

La rotación se realiza mediante el consumo de un estado mágico; es decir, una copia del estado $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .
\end{align} $ $

## <a name="input"></a>Entrada

### <a name="data--qubit"></a>datos: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit que se va a rotar sobre $Y $ por $ \pi/$4.


### <a name="magic--qubit"></a>Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Un qubit inicialmente en el estado mágico. La siguiente aplicación de esta operación `magic` se devuelve al estado $ \ket {0} $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Los siguientes son equivalentes:

```qsharp
Ry(PI() / 4.0, data);
```

y

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Esta operación admite el `Adjoint` functor, en cuyo caso se consume el mismo estado mágico, pero el efecto en el qubit de datos es un $-\ PI/4 $ $Y $-Rotation.