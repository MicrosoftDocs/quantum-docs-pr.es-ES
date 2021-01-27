---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: Operación ApplyMultiplyControlledLowDepthAnd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841670"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="641bc-102">Operación ApplyMultiplyControlledLowDepthAnd</span><span class="sxs-lookup"><span data-stu-id="641bc-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="641bc-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="641bc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="641bc-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="641bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="641bc-105">Implementa una puerta Toffoli de varios controlados, suponiendo que qubit de destino se inicializa 0.</span><span class="sxs-lookup"><span data-stu-id="641bc-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="641bc-106">La operación de "contiguo" supone que el qubit de destino se restablecerá a 0.</span><span class="sxs-lookup"><span data-stu-id="641bc-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="641bc-107">Requiere una profundidad RZ de 1, mientras que el número de qubits auxiliares es exponencial en el número de qubits.</span><span class="sxs-lookup"><span data-stu-id="641bc-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="641bc-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="641bc-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="641bc-109">controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="641bc-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="641bc-110">Qubits de control</span><span class="sxs-lookup"><span data-stu-id="641bc-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="641bc-111">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="641bc-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="641bc-112">Qubit de destino</span><span class="sxs-lookup"><span data-stu-id="641bc-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="641bc-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="641bc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

