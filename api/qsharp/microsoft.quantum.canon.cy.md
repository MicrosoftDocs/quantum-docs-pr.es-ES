---
uid: Microsoft.Quantum.Canon.CY
title: Operación CY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728781"
---
# <a name="cy-operation"></a>Operación CY

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Aplica la puerta controlada-Y (CY) a un par de qubits.

$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & 0 & \\ \\ -i \\ \\ 0 & 0 & i & 0 \end{align}, $ $, donde las filas y columnas están organizadas como en la guía de conceptos de Quantum.

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="control--qubit"></a>control: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Controle qubit para la puerta CY.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de destino para la puerta CY.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Equivalente a:

```qsharp
Controlled Y([control], target);
```