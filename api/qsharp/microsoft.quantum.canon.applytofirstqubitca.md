---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Operación ApplyToFirstQubitCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729225"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="e73a7-102">Operación ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="e73a7-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="e73a7-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e73a7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e73a7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e73a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e73a7-105">Aplica la operación OP al primer qubit del registro.</span><span class="sxs-lookup"><span data-stu-id="e73a7-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="e73a7-106">El modificador `CA` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="e73a7-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e73a7-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="e73a7-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="e73a7-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit) de => [unidad](xref:microsoft.quantum.lang-ref.unit) ajustable + CTL</span><span class="sxs-lookup"><span data-stu-id="e73a7-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="e73a7-109">Operación que se va a aplicar al primer qubit</span><span class="sxs-lookup"><span data-stu-id="e73a7-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e73a7-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e73a7-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e73a7-111">Matriz qubit al primer qubit del que se aplica la operación</span><span class="sxs-lookup"><span data-stu-id="e73a7-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="e73a7-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e73a7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e73a7-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e73a7-113">See Also</span></span>

- [<span data-ttu-id="e73a7-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="e73a7-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)