---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Operación pulso
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729741"
---
# <a name="applyand-operation"></a>Operación pulso

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Invierte un qubit de destino determinado si y solo si ambos qubits de control están en el estado 1, utilizando la medida para realizar la operación de la función de la función.

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>Descripción

Invierte `target` si y solo si ambos controles son 1, pero supone que `target` está en el estado 0.  La operación tiene T-Count 4, T-Depth 2 y no requiere qubit auxiliar y, por tanto, puede ser preferible a una operación CCNOT, si `target` se sabe que es 0.  El contiguo de esta operación se basa en medidas y no requiere ninguna de T.

La aplicación controlada de esta operación no requiere ningún qubit auxiliar, las `2^c` `Rz` puertas y no está optimizada para la profundidad, donde `c` es el número de qubits de control general, incluidos los dos controles de la `ApplyAnd` operación.  La aplicación controlada por el valor contiguo requiere las `2^c - 1` `Rz` puertas (con un ángulo dos veces el tamaño de la operación no contigua), no qubit de la aplicación auxiliar y no está optimizada para la profundidad.

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
- Craig Gidney: "en la mitad del costo de la suma de Quantum", Quantum 2, página 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) doi: 10.1103/PhysRevA. 85.044302
- Dittrich Soeken: "Quantum Oracle los circuitos y el patrón de árbol de Navidad", [artículo de blog del 19 de diciembre de 2019](https://msoeken.github.io/blog_qac.html) (Nota: explica la construcción controlada múltiple)