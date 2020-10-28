---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operación MultiplyByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730629"
---
# <a name="multiplybymodularinteger-operation"></a>Operación MultiplyByModularInteger

Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)

Configura [](https://nuget.org/packages/)


Realiza una multiplicación modular por una constante de tipo entero en un registro qubit.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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