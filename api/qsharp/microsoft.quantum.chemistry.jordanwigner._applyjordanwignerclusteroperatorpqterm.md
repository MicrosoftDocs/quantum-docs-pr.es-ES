---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQTerm
title: _ApplyJordanWignerClusterOperatorPQTerm operación
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQTerm
qsharp.summary: Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: 67ec6fcfec097a14b1e31f94ac82ecf15109ecf6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851738"
---
# <a name="_applyjordanwignerclusteroperatorpqterm-operation"></a><span data-ttu-id="c5c61-102">_ApplyJordanWignerClusterOperatorPQTerm operación</span><span class="sxs-lookup"><span data-stu-id="c5c61-102">_ApplyJordanWignerClusterOperatorPQTerm operation</span></span>

<span data-ttu-id="c5c61-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="c5c61-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="c5c61-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c5c61-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="c5c61-105">Aplica la evolución de la hora por un operador de clúster de PQ que describe un `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="c5c61-105">Applies time-evolution by a cluster operator PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c5c61-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c5c61-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="c5c61-107">término: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c5c61-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c5c61-108">`GeneratorIndex` que representa un término de PQ del operador de clúster.</span><span class="sxs-lookup"><span data-stu-id="c5c61-108">`GeneratorIndex` representing a cluster operator PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c5c61-109">Pasos: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c5c61-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c5c61-110">Duración de la evolución del tiempo.</span><span class="sxs-lookup"><span data-stu-id="c5c61-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c5c61-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c5c61-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c5c61-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="c5c61-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5c61-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5c61-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

