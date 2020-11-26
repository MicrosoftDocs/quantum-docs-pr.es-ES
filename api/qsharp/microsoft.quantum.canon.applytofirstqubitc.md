---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Operación ApplyToFirstQubitC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2659c3a97baa68cb4c1d7781381f89742902594d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217516"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="e1c12-102">Operación ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="e1c12-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="e1c12-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e1c12-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e1c12-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1c12-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1c12-105">Aplica la operación OP al primer qubit del registro.</span><span class="sxs-lookup"><span data-stu-id="e1c12-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="e1c12-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="e1c12-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="e1c12-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="e1c12-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="e1c12-108">OP: [Qubit](xref:microsoft.quantum.lang-ref.qubit) la => [unidad](xref:microsoft.quantum.lang-ref.unit) qubit es CTL</span><span class="sxs-lookup"><span data-stu-id="e1c12-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e1c12-109">Operación que se va a aplicar al primer qubit</span><span class="sxs-lookup"><span data-stu-id="e1c12-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e1c12-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e1c12-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e1c12-111">Matriz qubit al primer qubit del que se aplica la operación</span><span class="sxs-lookup"><span data-stu-id="e1c12-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1c12-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1c12-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e1c12-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1c12-113">See Also</span></span>

- [<span data-ttu-id="e1c12-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="e1c12-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)