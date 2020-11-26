---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Operación ApproximatelyMultiplexZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 5e254c2b2d6cbf29b428f4d55aef0e61356e3480
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217108"
---
# <a name="approximatelymultiplexz-operation"></a>Operación ApproximatelyMultiplexZ

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una rotación de Pauli Z condicionada en una matriz de qubits, truncando ángulos de rotación pequeños según una tolerancia determinada.

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

De esta forma se aplica la operación de unitario controlada multiplicación que realiza rotaciones por ángulo $ \ theta_j $ sobre el operador Pauli de un solo qubit $Z $ cuando lo controla el $n $-qubit Number $ \ket{j} $.
En concreto, esta operación se puede representar mediante la unitario

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.
\end{align} $ $

## <a name="input"></a>Entrada

### <a name="tolerance--double"></a>tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)

Tolerancia por debajo de la cual se truncan los coeficientes pequeños.


### <a name="coefficients--double"></a>coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matriz de hasta $2 ^ n $ coeficientes $ \ theta_j $. El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.


### <a name="control--littleendian"></a>control: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Registro de qubit único que gira $e ^ {i P \ theta_j} $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

`coefficients` se rellenará con los elementos $ \ theta_j = $0,0 si se especifican menos de $2 ^ n $.

## <a name="references"></a>Referencias

- Síntesis de los circuitos de lógica de Quantum Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. MultiplexZ](xref:Microsoft.Quantum.Canon.MultiplexZ)