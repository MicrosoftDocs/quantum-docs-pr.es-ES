---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Operación ApplyMultiplyControlledAnd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729465"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="2af04-102">Operación ApplyMultiplyControlledAnd</span><span class="sxs-lookup"><span data-stu-id="2af04-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="2af04-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2af04-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2af04-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2af04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2af04-105">Implementa una puerta Toffoli de varios controlados, suponiendo que qubit de destino se inicializa 0.</span><span class="sxs-lookup"><span data-stu-id="2af04-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="2af04-106">La operación de "contiguo" supone que el qubit de destino se restablecerá a 0.</span><span class="sxs-lookup"><span data-stu-id="2af04-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="2af04-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="2af04-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="2af04-108">controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2af04-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2af04-109">Qubits de control</span><span class="sxs-lookup"><span data-stu-id="2af04-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2af04-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2af04-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2af04-111">Qubit de destino</span><span class="sxs-lookup"><span data-stu-id="2af04-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="2af04-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2af04-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

