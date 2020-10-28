---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Operación ApplyToFirstQubitC
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729231"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="855af-102">Operación ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="855af-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="855af-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="855af-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="855af-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="855af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="855af-105">Aplica la operación OP al primer qubit del registro.</span><span class="sxs-lookup"><span data-stu-id="855af-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="855af-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="855af-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="855af-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="855af-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="855af-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [unidad](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="855af-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="855af-109">Operación que se va a aplicar al primer qubit</span><span class="sxs-lookup"><span data-stu-id="855af-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="855af-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="855af-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="855af-111">Matriz qubit al primer qubit del que se aplica la operación</span><span class="sxs-lookup"><span data-stu-id="855af-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="855af-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="855af-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="855af-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="855af-113">See Also</span></span>

- [<span data-ttu-id="855af-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="855af-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)