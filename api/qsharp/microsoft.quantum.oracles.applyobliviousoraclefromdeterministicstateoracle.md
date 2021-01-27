---
uid: Microsoft.Quantum.Oracles.ApplyObliviousOracleFromDeterministicStateOracle
title: Operación ApplyObliviousOracleFromDeterministicStateOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ApplyObliviousOracleFromDeterministicStateOracle
qsharp.summary: Implementation of <xref:microsoft.quantum.canon.obliviousoraclefromdeterministicstateoracle>.
ms.openlocfilehash: d9bc25129d6cf4755067f5fbe26f30a218302442
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854531"
---
# <a name="applyobliviousoraclefromdeterministicstateoracle-operation"></a><span data-ttu-id="02107-102">Operación ApplyObliviousOracleFromDeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="02107-102">ApplyObliviousOracleFromDeterministicStateOracle operation</span></span>

<span data-ttu-id="02107-103">Espacio de nombres: [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="02107-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="02107-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02107-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02107-105">Implementación de <xref:microsoft.quantum.canon.obliviousoraclefromdeterministicstateoracle>.</span><span class="sxs-lookup"><span data-stu-id="02107-105">Implementation of <xref:microsoft.quantum.canon.obliviousoraclefromdeterministicstateoracle>.</span></span>

```qsharp
operation ApplyObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, ancillaRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="02107-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="02107-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="02107-107">ancillaOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="02107-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>




### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="02107-108">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="02107-108">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>




### <a name="ancillaregister--qubit"></a><span data-ttu-id="02107-109">ancillaRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="02107-109">ancillaRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="systemregister--qubit"></a><span data-ttu-id="02107-110">systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="02107-110">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="02107-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02107-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

