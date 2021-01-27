---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definido por el usuario ReflectionOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854485"
---
# <a name="reflectionoracle-user-defined-type"></a>Tipo definido por el usuario ReflectionOracle

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Representa una reflexión de Oracle.

Una reflexión de Oracle, $O $, tiene entradas:

- Fase $ \phi $ por la que se va a girar el subespacio reflejado.
- Registro qubit en el que se va a realizar la reflexión determinada.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Elementos con nombre

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL



## <a name="remarks"></a>Observaciones

Esta $O de Oracle = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ realiza una reflexión parcial en una fase $ \phi $ sobre un único estado puro $ \ket{\psi} $.