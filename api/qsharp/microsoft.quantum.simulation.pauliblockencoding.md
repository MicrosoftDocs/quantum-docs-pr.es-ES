---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730916"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="e23bd-102">PauliBlockEncoding función)</span><span class="sxs-lookup"><span data-stu-id="e23bd-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="e23bd-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e23bd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e23bd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e23bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e23bd-105">Crea una unidad de codificación de bloques para un Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="e23bd-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="e23bd-106">El Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ se describe mediante una suma de los términos de Pauli $P _j $, cada uno con coeficiente real $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="e23bd-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="e23bd-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="e23bd-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="e23bd-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e23bd-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="e23bd-109">`GeneratorSystem`Que describe $H $ como suma de los términos de Pauli</span><span class="sxs-lookup"><span data-stu-id="e23bd-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="e23bd-110">Salida: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="e23bd-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="e23bd-111">Primer parámetro</span><span class="sxs-lookup"><span data-stu-id="e23bd-111">First parameter</span></span>

<span data-ttu-id="e23bd-112">La única norma de los coeficientes $ \alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="e23bd-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="e23bd-113">Segundo parámetro</span><span class="sxs-lookup"><span data-stu-id="e23bd-113">Second parameter</span></span>

<span data-ttu-id="e23bd-114">Un `BlockEncodingReflection` unitario $U $ de Hamiltonian $H $.</span><span class="sxs-lookup"><span data-stu-id="e23bd-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="e23bd-115">Como esta unitario cumple $U ^ 2 = I $, también es una reflexión.</span><span class="sxs-lookup"><span data-stu-id="e23bd-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="e23bd-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e23bd-116">Remarks</span></span>

<span data-ttu-id="e23bd-117">Esto se obtiene al preparar y despreparar el estado $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ y construir una unitario controlada por multiplicación <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> y <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="e23bd-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>