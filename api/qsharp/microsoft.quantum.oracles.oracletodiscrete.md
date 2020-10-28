---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733357"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete función)

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Configura [](https://nuget.org/packages/)


Dada una operación que representa una "caja negra" de Oracle, devuelve una Oracle de tiempo discreto que representa el valor de Oracle "Black-Box" repetido varias veces.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Entrada

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a>blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Operación que se va a un exponente.



## <a name="output--discreteoracle"></a>Salida: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operación parcialmente aplicada en el "cuadro negro" que representa el Oracle de tiempo discreto