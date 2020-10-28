---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definido por el usuario ReflectionOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733340"
---
# <a name="reflectionoracle-user-defined-type"></a>Tipo definido por el usuario ReflectionOracle

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Configura [](https://nuget.org/packages/)


Representa una reflexión de Oracle.

Una reflexión de Oracle, $O $, tiene entradas:

- Fase $ \phi $ por la que se va a girar el subespacio reflejado.
- Registro qubit en el que se va a realizar la reflexión determinada.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Elementos con nombre

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL



## <a name="remarks"></a>Observaciones

Esta $O de Oracle = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ realiza una reflexión parcial en una fase $ \phi $ sobre un único estado puro $ \ket{\psi} $.