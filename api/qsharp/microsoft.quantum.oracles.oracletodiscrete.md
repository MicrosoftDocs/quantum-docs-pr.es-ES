---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193852"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete función)

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una operación que representa una "caja negra" de Oracle, devuelve una Oracle de tiempo discreto que representa el valor de Oracle "Black-Box" repetido varias veces.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Entrada

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL

Operación que se va a un exponente.



## <a name="output--discreteoracle"></a>Salida: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operación parcialmente aplicada en el "cuadro negro" que representa el Oracle de tiempo discreto