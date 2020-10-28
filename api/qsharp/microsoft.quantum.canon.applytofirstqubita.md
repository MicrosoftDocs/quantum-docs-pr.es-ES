---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: Operación ApplyToFirstQubitA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729230"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="cf56e-102">Operación ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="cf56e-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="cf56e-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cf56e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cf56e-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf56e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf56e-105">Aplica una operación a la primera qubit del registro.</span><span class="sxs-lookup"><span data-stu-id="cf56e-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="cf56e-106">El modificador `A` indica que la operación es adjointable.</span><span class="sxs-lookup"><span data-stu-id="cf56e-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cf56e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="cf56e-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="cf56e-108">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit) de => [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf56e-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="cf56e-109">Operación que se va a aplicar al primer qubit</span><span class="sxs-lookup"><span data-stu-id="cf56e-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="cf56e-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cf56e-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cf56e-111">Matriz qubit al primer qubit del que se aplica la operación</span><span class="sxs-lookup"><span data-stu-id="cf56e-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf56e-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf56e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="cf56e-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf56e-113">See Also</span></span>

- [<span data-ttu-id="cf56e-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="cf56e-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)