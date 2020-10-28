---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Operación ApplyPermutationUsingDecomposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 40b51807da155c57c3fa8d740eff28ceef0a0ffc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733972"
---
# <a name="applypermutationusingdecomposition-operation"></a>Operación ApplyPermutationUsingDecomposition

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Configura [](https://nuget.org/packages/)


Permute las amplitudes en un estado de Quantum dada una permutación mediante la síntesis basada en la descomposición.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descripción

Este procedimiento implementa el enfoque de síntesis basado en la descomposición.  La entrada es una permutación $ \pi $ sobre $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, que representa una función booleana $n $-variable reversible.
El algoritmo realiza de forma iterativa los pasos siguientes para cada índice de variable $i $:

1. Compute $ ((\ pi_l, \ pi_r), \pi ') $ tal que las imágenes de $ \ pi_l $ y $ \ pi_r $ no cambian los bits en sus elementos en índices distintos de $i $ e imágenes de $ \pi ' $ no cambian el bit $i $ en sus elementos.
2. Establezca $ \pi \leftarrow \pi $ y derive las tablas de verdad de $ \ pi_l $ y $ \ pi_r $ basándose en elementos que no son de puntos fijos.

Después de aplicar estos pasos para todos los índices de variables, la permutación restante $ \pi $ será la identidad y, en función de los índices y las tablas reales recopilados, puede aplicar operaciones controladas por la tabla de verdad @"microsoft.quantum.intrinsic.x" mediante la @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operación.

El orden de las variables es $0, \dots, n-$1.  Se puede especificar un orden de variable personalizado en la operación @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .

## <a name="input"></a>Entrada

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]

Una permutación de $2 ^ n $ elementos a partir de 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Una lista de $n $ qubits a la que se aplica la permutación.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencias

- [*Alexis de vos* , *Yvan van Rentergem* , ADV. en Math. of COMM. 2 (2), 2008, PP. 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Dittrich Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , Journal of simbólica Calculation 73 (2016), PP. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecompositionWithVariableOrder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)