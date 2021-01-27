---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: c27ef1a6b7cd7c84defe2a783e9fb1610e52d1e7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851077"
---
# <a name="_pauliblockencoding-function"></a>_PauliBlockEncoding función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea una unidad de codificación de bloques para un Hamiltonian.

El Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ se describe mediante una suma de los términos de Pauli $P _j $, cada uno con coeficiente real $ \ alpha_j $.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Entrada

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Que describe $H $ como suma de los términos de Pauli


### <a name="stateprepunitary--double---littleendian--unit--is-adj--ctl"></a>statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [unidad](xref:microsoft.quantum.lang-ref.unit) LittleEndian es ADJ + CTL

Operación unitario $V $ que aplica la $V unitario _j $ controlada en el índice $ \ket{j} $, dada una función $f: j\rightarrow V_j $.


### <a name="multiplexer--intint---qubit--unit--is-adj--ctl---littleendianqubit--unit--is-adj--ctl"></a>multiplexor: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL





## <a name="output--doubleblockencodingreflection"></a>Salida: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Primer parámetro

La única norma de los coeficientes $ \alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Segundo parámetro

Un `BlockEncodingReflection` unitario $U $ de Hamiltonian $U $. Como esta unitario cumple $U ^ 2 = I $, también es una reflexión.

## <a name="remarks"></a>Observaciones

Operaciones de ejemplo: preparar y despreparar el estado $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ y construir una unitario controlada por multiplicación son <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> y <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .