---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726339"
---
# <a name="_pauliblockencoding-function"></a>_PauliBlockEncoding función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Configura [](https://nuget.org/packages/)


Crea una unidad de codificación de bloques para un Hamiltonian.

El Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ se describe mediante una suma de los términos de Pauli $P _j $, cada uno con coeficiente real $ \ alpha_j $.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Entrada

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Que describe $H $ como suma de los términos de Pauli


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a>statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) ajustable + CTL

Operación unitario $V $ que aplica la $V unitario _j $ controlada en el índice $ \ket{j} $, dada una función $f: j\rightarrow V_j $.


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a>multiplexor: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => ajuste de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL





## <a name="output--doubleblockencodingreflection"></a>Salida: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Primer parámetro

La única norma de los coeficientes $ \alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Segundo parámetro

Un `BlockEncodingReflection` unitario $U $ de Hamiltonian $U $. Como esta unitario cumple $U ^ 2 = I $, también es una reflexión.

## <a name="remarks"></a>Observaciones

Operaciones de ejemplo: preparar y despreparar el estado $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ y construir una unitario controlada por multiplicación son <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> y <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .