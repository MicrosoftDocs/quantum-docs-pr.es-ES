---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Operación QuantumPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839670"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="4ad90-102">Operación QuantumPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="4ad90-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="4ad90-103">Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="4ad90-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="4ad90-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ad90-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ad90-105">Realiza el algoritmo de estimación de fase de Quantum para una determinada Oracle `U` y `targetState` lee la fase en un registro Quantum Big-Endian.</span><span class="sxs-lookup"><span data-stu-id="4ad90-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4ad90-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4ad90-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="4ad90-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="4ad90-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="4ad90-108">Una operación que implementa $U ^ m $ para un entero determinado potencia m.</span><span class="sxs-lookup"><span data-stu-id="4ad90-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="4ad90-109">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4ad90-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4ad90-110">Un registro de Quantum que representa el estado $ \ket{\phi} $ en el que actuó $U $.</span><span class="sxs-lookup"><span data-stu-id="4ad90-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="4ad90-111">Si $ \ket{\phi} $ es un eigenstate de $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ para $ \phi \en [0, 2 \ PI) $ una fase desconocida.</span><span class="sxs-lookup"><span data-stu-id="4ad90-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="4ad90-112">controlRegister: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="4ad90-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="4ad90-113">Un registro entero de representación Big-Endian que se puede utilizar para controlar la Oracle proporcionada y que contendrá la representación de $ \phi $ después de la aplicación de esta operación.</span><span class="sxs-lookup"><span data-stu-id="4ad90-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="4ad90-114">Se supone que el controlRegister se inicia en el estado inicial $ \ket{00\cdots 0} $, donde la longitud del registro indica la precisión deseada.</span><span class="sxs-lookup"><span data-stu-id="4ad90-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ad90-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ad90-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

