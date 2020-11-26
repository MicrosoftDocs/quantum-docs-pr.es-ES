---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ccef1bbf400e01800053777d0010acb7addaef53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192492"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convierte una reflexión de codificación de bloques en un recorrido de Quantum.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Descripción

Dado un `BlockEncodingReflection` representado por un valor unitario $U $ que codifica algún operador $H $ de interés, lo convierte en un recorrido de quantum $W $ que contiene el espectro de $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="input"></a>Entrada

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Un `BlockEncodingReflection` unitario $U $ que se va a convertir en un recorrido de Quantum.



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL

Un recorrido de Quantum $W $ actuando conjuntamente en los registros `a` y `s` que codifica en bloque $H $, y contiene el espectro de $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="references"></a>Referencias

- Hamiltonian Simulation Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)