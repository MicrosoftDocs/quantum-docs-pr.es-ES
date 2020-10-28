---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorImpl
title: _JordanWignerClusterOperatorImpl operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 9507558ebe73bce87d9089aad22b94c1d9d579d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728030"
---
# <a name="_jordanwignerclusteroperatorimpl-operation"></a><span data-ttu-id="d75a6-102">_JordanWignerClusterOperatorImpl operación</span><span class="sxs-lookup"><span data-stu-id="d75a6-102">_JordanWignerClusterOperatorImpl operation</span></span>

<span data-ttu-id="d75a6-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d75a6-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d75a6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d75a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d75a6-105">Representa un generador dinámico como un conjunto de puertas simulables y una expansión en la base de JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="d75a6-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="d75a6-106">Para obtener más información, vea [modelado de generador dinámico](../libraries/data-structures#dynamical-generator-modeling) .</span><span class="sxs-lookup"><span data-stu-id="d75a6-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JordanWignerClusterOperatorImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d75a6-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d75a6-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="d75a6-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="d75a6-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="d75a6-109">Índice de generador que se va a representar como una evolución de la unitario en el JordanWigner.</span><span class="sxs-lookup"><span data-stu-id="d75a6-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="d75a6-110">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d75a6-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d75a6-111">Variable ficticia para hacer coincidir la firma de los algoritmos de simulación.</span><span class="sxs-lookup"><span data-stu-id="d75a6-111">Dummy variable to match signature of simulation algorithms.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d75a6-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d75a6-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d75a6-113">Registro actuado por el operador de evolución de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d75a6-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d75a6-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d75a6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

