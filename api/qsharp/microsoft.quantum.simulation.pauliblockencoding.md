---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: b1df6d239e6ef061cf0a4784c652e9dd126991d5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230436"
---
# <a name="pauliblockencoding-function"></a>PauliBlockEncoding función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea una unidad de codificación de bloques para un Hamiltonian.

El Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ se describe mediante una suma de los términos de Pauli $P _j $, cada uno con coeficiente real $ \ alpha_j $.

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Entrada

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Que describe $H $ como suma de los términos de Pauli



## <a name="output--doubleblockencodingreflection"></a>Salida: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Primer parámetro

La única norma de los coeficientes $ \alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Segundo parámetro

Un `BlockEncodingReflection` unitario $U $ de Hamiltonian $H $. Como esta unitario cumple $U ^ 2 = I $, también es una reflexión.

## <a name="remarks"></a>Observaciones

Esto se obtiene al preparar y despreparar el estado $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ y construir una unitario controlada por multiplicación <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> y <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .