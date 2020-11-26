---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Operación PrepareUniformSuperposition
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 9b9f182ed7c1ea24ae74b8a2321a309042a17c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230096"
---
# <a name="prepareuniformsuperposition-operation"></a>Operación PrepareUniformSuperposition

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea una superposición uniforme sobre los Estados que codifican 0 a `nIndices - 1` .

Es decir, esta $U unitario $ crea una superposición uniforme sobre todos los Estados $0 $ en $M-$1, dado un estado de entrada $ \ket{0\cdots 0} $. En otras palabras, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.
\end{align} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="nindices--int"></a>nIndices: [int](xref:microsoft.quantum.lang-ref.int)

El número deseado de Estados $M $ en la superposición uniforme.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

El registro qubit que almacena los Estados de número en `LittleEndian` formato.
Este registro debe ser capaz de almacenar el número $M-$1 y se supone que se ha inicializado en el estado $ \ket{0\cdots 0} $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

La operación es adjointable, pero requiere que `indexRegister` esté en una superposición uniforme `nIndices` en los Estados de la primera base en ese caso.