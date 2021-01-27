---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState operación
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830983"
---
# <a name="_prepareentangledstate-operation"></a>_prepareEntangledState operación

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Dados dos registros, prepara el estado con una limitación máxima entre cada par de qubits en los registros respectivos.
Todos los qubits deben comenzar en el estado | 0 ⟩.

El resultado es que los pares correspondientes de qubits de cada registro se encuentran en $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $.

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="left--qubit"></a>izquierda: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Una matriz qubit en el estado $ \ket{0\cdots 0} $


### <a name="right--qubit"></a>Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Una matriz qubit en el estado $ \ket{0\cdots 0} $



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)

