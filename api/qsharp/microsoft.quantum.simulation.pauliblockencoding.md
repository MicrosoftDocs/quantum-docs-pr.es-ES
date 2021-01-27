---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848014"
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