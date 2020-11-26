---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: Operación PrepareArbitraryState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > PrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18a1e86f8e110a8f48d7dd50961e1f1f471ffc4e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190707"
---
# <a name="preparearbitrarystate-operation"></a>Operación PrepareArbitraryState

Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> PrepareArbitraryState está en desuso. Use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> en su lugar.

Dado un conjunto de coeficientes y un registro de Quantum con codificación Little-endian, prepara un estado en ese registro descrito por los coeficientes proporcionados.

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Esta operación prepara un estado de Quantum arbitrario $ \ket{\psi} $ con coeficientes complejos $r _j e ^ {i t_j} $ del estado de la base de cálculo $n $-qubit $ \ket{0 \cdots 0} $.
En concreto, la acción de esta operación la puede simular una transformación unitario $U $ que actúa en el estado de todos los ceros como

$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{align} $ $

## <a name="input"></a>Entrada

### <a name="coefficients--complexpolar"></a>coeficientes: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Matriz de hasta $2 ^ n $ coeficientes complejos representados por su valor absoluto y la fase $ (r_j, t_j) $. El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit registra los Estados de número de codificación en formato Little-Endian. Se espera que se inicialice en el estado de base de cálculo $ \ket{0...0} $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Los coeficientes de entrada negativos $r _j < $0 se tratarán como positivos con el valor $ | r_j | $. `coefficients` se rellenará con los elementos $ (r_j, t_j) = (0,0, 0,0) $ si se especifican menos de $2 ^ n $.

## <a name="references"></a>Referencias

- Síntesis de los circuitos de lógica de Quantum Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. preparación. ApproximatelyPrepareArbitraryState](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)