---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: Operación MultiplexPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: 656b510cb19af69a9a3f0d537d54b0abfe76de4b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852446"
---
# <a name="multiplexpauli-operation"></a>Operación MultiplexPauli

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una rotación Pauli condicionada en una matriz de qubits.

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Esto aplica una operación de unitarios controlada multiplicación que realiza rotaciones por ángulo $ \ theta_j $ sobre el operador Pauli de un solo qubit $P $ cuando lo controla el $n $-qubit Number $ \ket{j} $.
En concreto, la acción de esta operación está representada por la unitario

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.
\end{align} $ $

## <a name="input"></a>Entrada

### <a name="coefficients--double"></a>coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matriz de hasta $2 ^ n $ coeficientes $ \ theta_j $. El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.


### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operador Pauli $P $ que determina el eje de giro.


### <a name="control--littleendian"></a>control: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Registro de qubit único que gira $e ^ {i P \ theta_j} $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

`coefficients` se rellenará con los elementos $ \ theta_j = $0,0 si se especifican menos de $2 ^ n $.

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Canon. ApproximatelyMultiplexPauli](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)