---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: Operación ApplyToFirstQubitC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: a36d20e03ebed82435d1d4136f4ce777eb468926
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850715"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="1ddda-102">Operación ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="1ddda-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="1ddda-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1ddda-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1ddda-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ddda-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1ddda-105">Aplica la operación OP al primer qubit del registro.</span><span class="sxs-lookup"><span data-stu-id="1ddda-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="1ddda-106">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="1ddda-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="1ddda-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="1ddda-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="1ddda-108">OP: [](xref:microsoft.quantum.lang-ref.qubit) la => [unidad](xref:microsoft.quantum.lang-ref.unit) qubit es CTL</span><span class="sxs-lookup"><span data-stu-id="1ddda-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1ddda-109">Operación que se va a aplicar al primer qubit</span><span class="sxs-lookup"><span data-stu-id="1ddda-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="1ddda-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1ddda-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1ddda-111">Matriz qubit al primer qubit del que se aplica la operación</span><span class="sxs-lookup"><span data-stu-id="1ddda-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ddda-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ddda-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="1ddda-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ddda-113">See Also</span></span>

- [<span data-ttu-id="1ddda-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="1ddda-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)