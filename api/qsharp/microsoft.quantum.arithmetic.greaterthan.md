---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: Operación GreaterThan
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 644d68affbdb508938f76de5025a1a463e7284e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223092"
---
# <a name="greaterthan-operation"></a>Operación GreaterThan

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica una comparación mayor que entre dos enteros codificados en registros de qubit, volteando un qubit de destino basándose en el resultado de la comparación.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Lleva a cabo un valor estrictamente mayor que la comparación de dos enteros $x $ y $y $, codificados en qubit registra XS y calendario. Si $x > y $, se volteará el resultado qubit; de lo contrario, el resultado qubit mantendrá su estado.

## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra el primer entero $x $.


### <a name="ys--littleendian"></a>calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra el segundo entero $y $.


### <a name="result--qubit"></a>resultado: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit único que se va a voltear si $x > y $.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Utiliza el truco que $x-y = (x ' + y) ' $, donde ' denota el complemento de uno.

## <a name="references"></a>Referencias

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "un nuevo circuito de adición del transporte de onda de Quantum", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas Haener, Martin Roetteler, KRYSTA M. Svore: "factoring Using 2N + 2 qubits con la multiplicación modular basada en Toffoli", 2016 https://arxiv.org/abs/1611.07995