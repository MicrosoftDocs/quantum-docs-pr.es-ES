---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 254ace01750f94e6c871de9b62f1342000bc84ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229552"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Codifica un operador de interés en un `BlockEncoding` .

Esto crea una `BlockEncoding` $U unitario = P\cdot V\cdot P ^ \dagger $ que codifica algún operador $H = \ sum_ {j} | \ alpha_j | U_j $ de interés que es una combinación lineal de unitaries. Normalmente, $P $ es una unitario de preparación de estado de forma que $P \ket {0} \_ a = \ sum_j \vec\alpha alpha_j \sqrt{\/ \| \| \_ 2} \ket{j} \_ a $ y $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

$P unitario $ que prepara algún Estado de destino.


### <a name="selector--ts--unit--is-adj--ctl"></a>Selector: (' t, ') => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

$V unitario $ que codifica el componente unitaries de $H $.



## <a name="output--ts--unit--is-adj--ctl"></a>Output: (' t, ') => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL

Una unidad $U $ actuando conjuntamente en los registros `a` y `s` que codifica en bloque $H $ y cumple $U ^ \Dagger = U $.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada


### <a name="s"></a>Hoy



## <a name="remarks"></a>Observaciones

Esta `BlockEncoding` implementación proporciona las propiedades de un `BlockEncodingReflection` .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)