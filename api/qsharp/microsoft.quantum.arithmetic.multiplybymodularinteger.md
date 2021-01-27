---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operación MultiplyByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846505"
---
# <a name="multiplybymodularinteger-operation"></a>Operación MultiplyByModularInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza una multiplicación modular por una constante de tipo entero en un registro qubit.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Díganos `modulus` $N $ y `constMultiplier` $a $.
Después, esta operación implementa una operación unitario definida por la siguiente asignación en la base de cálculo: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ para todos los $y $ entre $0 $ y $N-$1.

## <a name="input"></a>Entrada

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Constante por la que se va a multiplicar el multiplicador. Debe ser cofundador para el módulo.


### <a name="modulus--int"></a>módulo: [int](xref:microsoft.quantum.lang-ref.int)

La operación de multiplicación se realiza en módulo `modulus` .


### <a name="multiplier--littleendian"></a>multiplicador: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Número que se va a multiplicar por una constante.
Se trata de una matriz de qubits que codifica un entero en formato Little-Endian.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

- En el diagrama de circuitos y la explicación, consulte la figura 7 en la [Página 8 de arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- Esta operación corresponde a U ₐ en [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)