---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState operación
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 97a55b4bb85095c7d8e8432dfcd1c6d6f7e93cdc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223942"
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

