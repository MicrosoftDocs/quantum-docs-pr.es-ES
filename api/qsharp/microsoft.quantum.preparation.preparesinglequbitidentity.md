---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Operación PrepareSingleQubitIdentity
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193631"
---
# <a name="preparesinglequbitidentity-operation"></a>Operación PrepareSingleQubitIdentity

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prepara un qubit en el estado de máxima mezcla.

Prepara el qubit determinado en el estado $ \boldone/$2 mediante la aplicación del canal de despolar $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \en \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ Where $ \sigma \_ i $ es el $i operador $ TH Pauli y donde $ \rho $ es un operador de densidad que representa un estado mixto.

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Un qubit cuyo estado se va a despolar de la manera descrita anteriormente.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

El estado mixto $ \boldone/$2 que describe el resultado de aplicar esta operación a un estado describe implícitamente un valor de expectativa sobre las elecciones aleatorias realizadas en esta operación.
Por lo tanto, para una sola aplicación, esta operación asigna Estados puros a Estados puros, pero actúa como se describe en expectativa.
En concreto, esta operación se puede usar en el proceso Tomography para medir los componentes *no unitarios* de un canal.