---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Operación de multiplicación
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 96922f0147788b37cc9bace5154288a722d4ba95
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222514"
---
# <a name="multiplyi-operation"></a>Operación de multiplicación

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Multiplique el entero `xs` por un entero `ys` y almacene el resultado en `result` , que debe ser cero inicialmente.

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit multiplicando (LittleEndian)


### <a name="ys--littleendian"></a>calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n multiplicador de $ bits (LittleEndian)


### <a name="result--littleendian"></a>resultado: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

el resultado de $2N $-bit (LittleEndian) debe estar en el estado $ \ket {0} $ inicialmente.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

Utiliza un enfoque estándar de desplazamiento y adición para implementar la multiplicación.
La versión controlada se mejoró mediante la copia de $x _i $ en una ancilla qubit condicionada en el control qubits y, a continuación, el control de la adición en el ancilla qubit.