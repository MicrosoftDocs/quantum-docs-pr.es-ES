---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731109"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer función)

Espacio de nombres: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Configura [](https://nuget.org/packages/)


Devuelve una matriz de rotaciones de control individual a lo largo de un eje determinado, organizadas cíclicamente por un registro de qubits y parametrizado por parámetros de modelo distintos.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

El número de qubits en función de la capa especificada.


### <a name="axis--pauli"></a>eje: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Eje de giro de cada giro de la capa especificada.


### <a name="stride--int"></a>STRIDE: [int](xref:microsoft.quantum.lang-ref.int)

La separación entre el destino y los índices de control para cada rotación.



## <a name="output--controlledrotation"></a>Salida: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Una matriz de rotaciones controladas de dos qubits que se distribuyen cíclicamente a lo largo de un registro de `nQubits` qubits.