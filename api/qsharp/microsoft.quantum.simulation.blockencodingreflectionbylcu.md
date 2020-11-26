---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: e1247d961a7ebce798106c24c46d924dd6e6d347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229484"
---
# <a name="blockencodingreflectionbylcu-function"></a>BlockEncodingReflectionByLCU función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Codifica un operador de interés en un `BlockEncodingReflection` .

Esto crea una `BlockEncodingReflection` $U unitario = P\cdot V\cdot P ^ \dagger $ que codifica algún operador $H = \ sum_ {j} | \ alpha_j | U_j $ de interés que es una combinación lineal de unitaries. Normalmente, $P $ es una unitario de preparación de estado que $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ y $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Entrada

### <a name="statepreparation--qubit--unit--is-adj--ctl"></a>statePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL

$P unitario $ que prepara algún Estado de destino.


### <a name="selector--qubitqubit--unit--is-adj--ctl"></a>Selector: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL

$V unitario $ que codifica el componente unitaries de $H $.



## <a name="output--blockencodingreflection"></a>Salida: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Una unidad $U $ actuando conjuntamente en los registros `a` y `s` que codifica en bloque $H $ y cumple $U ' ^ {-1} = U $.

## <a name="remarks"></a>Observaciones

Esta `BlockEncoding` implementación proporciona las propiedades de un `BlockEncodingReflection` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)