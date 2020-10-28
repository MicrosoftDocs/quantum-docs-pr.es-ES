---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: Operación ApplyLowDepthAnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 092a350e42d8d90942de13530fefd761b5187e1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729477"
---
# <a name="applylowdepthand-operation"></a>Operación ApplyLowDepthAnd

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Invierte un qubit de destino determinado si y solo si ambos qubits de control están en el estado 1, con la profundidad de T 1, usando la medida para realizar la operación de la función de "contiguo".

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>Descripción

Invierte `target` si y solo si ambos controles son 1, pero supone que `target` está en el estado 0.  La operación tiene T-Count 4, T-Depth 1 y requiere un qubit auxiliar y, por tanto, es preferible a una operación CCNOT, si `target` se sabe que es 0.  El colindante de esta operación se basa en medidas y no requiere ninguna de T, y no se qubit la aplicación auxiliar.

## <a name="input"></a>Entrada

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primer control qubit


### <a name="control2--qubit"></a>control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Segundo control qubit


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Destino de qubit auxiliar; debe estar en el estado 0



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencias

- Cody Jones: "nuevas construcciones para la puerta de Toffoli tolerante a errores", físico Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) doi: 10.1103/PhysRevA. 87.022328
- Peter Selinger: "Quantum los circuitos de T-Depth One",-inv. Rev. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA. 87.042302