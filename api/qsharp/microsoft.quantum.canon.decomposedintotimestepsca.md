---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728774"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Devuelve una operación que implementa el integrador Trotter – Suzuki para una operación determinada.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)

El número de operaciones que se van a descomponer en pasos temporales.


### <a name="op--intdoublet--unit-adj--ctl"></a>OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), ' t) => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Una operación que acepta una entrada de índice (tipo `Int` ) y una entrada de hora (tipo `Double` ) para la descomposición.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Selecciona el orden del integrador Trotter – Suzuki que se va a usar.
Orden 1 e incluso pedidos 2, 4, 6,... Actualmente se admiten.



## <a name="output--doublet--unit-adj--ctl"></a>Salida: ([Double](xref:microsoft.quantum.lang-ref.double), ' t) => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL

Devuelve una unitario que implementa el integrador Trotter – Suzuki, donde el primer parámetro `Double` es el tamaño del paso de integración y el segundo parámetro es el destino sobre el que se actuó.

## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada

Tipo en el que debe actuar cada paso de tiempo; Normalmente, `Qubit[]` o `Qubit` .

## <a name="remarks"></a>Observaciones

Cuando se llama con `order` igual a `1` , esta función devuelve una operación que se puede simular con el orden más bajo Trotter – Suzuki Integrator $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $, donde hemos seguido la notación de [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) y dejar que $ \lambda $ sea la hora de la evolución (representada por la primera entrada de la operación devuelta). y tienen que dejar que $ \{ H_j \} _ {j = 1} ^ {m} $ sea el conjunto de generadores dinámicos (sesgado-Hermitian) que se integran de forma que `op(j, lambda, _)` se simula mediante el operador unitario $e ^ {H_j \lambda} $.

De forma similar, un `order` de `2` devuelve el segundo orden simétrico Trotter – Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.
\end{align} $ $

Los valores pares más altos de `order` se implementan mediante la construcción recursiva de [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).

## <a name="references"></a>Referencias

- [*D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)