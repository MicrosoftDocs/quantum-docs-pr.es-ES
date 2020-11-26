---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: Operación ApplyMultiplyControlledAnd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: 17a757278500833bc5a5d0635af020cfe1fd569f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218400"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="f2b43-102">Operación ApplyMultiplyControlledAnd</span><span class="sxs-lookup"><span data-stu-id="f2b43-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="f2b43-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2b43-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2b43-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2b43-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2b43-105">Implementa una puerta Toffoli de varios controlados, suponiendo que qubit de destino se inicializa 0.</span><span class="sxs-lookup"><span data-stu-id="f2b43-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="f2b43-106">La operación de "contiguo" supone que el qubit de destino se restablecerá a 0.</span><span class="sxs-lookup"><span data-stu-id="f2b43-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f2b43-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="f2b43-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="f2b43-108">controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f2b43-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f2b43-109">Qubits de control</span><span class="sxs-lookup"><span data-stu-id="f2b43-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f2b43-110">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f2b43-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f2b43-111">Qubit de destino</span><span class="sxs-lookup"><span data-stu-id="f2b43-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2b43-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2b43-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

