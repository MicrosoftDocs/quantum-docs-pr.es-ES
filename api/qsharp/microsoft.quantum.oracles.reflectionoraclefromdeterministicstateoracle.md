---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: 09de63d615a4d80e2b59deeddc07567aefe7660e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193835"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle función)

Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Construye la reflexión sobre un estado determinado desde Oracle.

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>Descripción

Dada una preparación de estado determinista de Oracle representada por una matriz de unitarios $O $, el resultado de esta función es una Oracle que aplica un reflejo en torno al estado $ \ket{\psi} $ preparado por Oracle $O $; es decir, el estado $ \ket{\psi} $, que $O \ket {0} = \ket{\psi} $.

## <a name="input"></a>Entrada

### <a name="oracle--deterministicstateoracle"></a>Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Oracle que prepara copias del estado $ \ket{\psi} $.



## <a name="output--reflectionoracle"></a>Salida: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Oracle que refleja el estado $ \ket{\psi} $.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Oracle. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. Oracle. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)