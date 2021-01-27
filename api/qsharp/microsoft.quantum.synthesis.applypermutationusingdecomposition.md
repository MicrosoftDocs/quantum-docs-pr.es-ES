---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Operación ApplyPermutationUsingDecomposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857393"
---
# <a name="applypermutationusingdecomposition-operation"></a>Operación ApplyPermutationUsingDecomposition

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permute las amplitudes en un estado de Quantum dada una permutación mediante la síntesis basada en la descomposición.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
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



## <a name="example"></a>Ejemplo

Para sintetizar una `SWAP` operación:

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>Referencias

- [*Alexis de vos*, *Yvan van Rentergem*, ADV. en Math. of COMM. 2 (2), 2008, PP. 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Dittrich Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of simbólica Calculation 73 (2016), PP. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecompositionWithVariableOrder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)