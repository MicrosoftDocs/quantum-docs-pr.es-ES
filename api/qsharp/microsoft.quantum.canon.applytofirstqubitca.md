---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: Operación ApplyToFirstQubitCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: ba82199cc7a548d771027141780873c05de71c57
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841429"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="eea2c-102">Operación ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="eea2c-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="eea2c-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eea2c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eea2c-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eea2c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eea2c-105">Aplica la operación OP al primer qubit del registro.</span><span class="sxs-lookup"><span data-stu-id="eea2c-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="eea2c-106">El modificador `CA` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="eea2c-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="eea2c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="eea2c-107">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="eea2c-108">OP: [](xref:microsoft.quantum.lang-ref.qubit) la => [unidad](xref:microsoft.quantum.lang-ref.unit) qubit es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="eea2c-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="eea2c-109">Operación que se va a aplicar al primer qubit</span><span class="sxs-lookup"><span data-stu-id="eea2c-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="eea2c-110">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="eea2c-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="eea2c-111">Matriz qubit al primer qubit del que se aplica la operación</span><span class="sxs-lookup"><span data-stu-id="eea2c-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="eea2c-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eea2c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="eea2c-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eea2c-113">See Also</span></span>

- [<span data-ttu-id="eea2c-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="eea2c-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)