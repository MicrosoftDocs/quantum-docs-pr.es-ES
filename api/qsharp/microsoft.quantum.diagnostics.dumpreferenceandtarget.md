---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: Operación DumpReferenceAndTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: f791f6f1e3c1b1da14ac3548a4bd78bb4f24ff83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727280"
---
# <a name="dumpreferenceandtarget-operation"></a><span data-ttu-id="cc7c7-102">Operación DumpReferenceAndTarget</span><span class="sxs-lookup"><span data-stu-id="cc7c7-102">DumpReferenceAndTarget operation</span></span>

<span data-ttu-id="cc7c7-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cc7c7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cc7c7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cc7c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cc7c7-105">Usa DumpRegister para proporcionar diagnósticos sobre el estado de una referencia y un registro de destino.</span><span class="sxs-lookup"><span data-stu-id="cc7c7-105">Uses DumpRegister to provide diagnostics on the state of a reference and target register.</span></span> <span data-ttu-id="cc7c7-106">Se escribe como una operación independiente para permitir el reemplazo e interpretación como registros independientes, en lugar de como un único registro combinado.</span><span class="sxs-lookup"><span data-stu-id="cc7c7-106">Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.</span></span>

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cc7c7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cc7c7-107">Input</span></span>

### <a name="reference--qubit"></a><span data-ttu-id="cc7c7-108">Referencia: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cc7c7-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="cc7c7-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cc7c7-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="cc7c7-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc7c7-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

