---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728871"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="cf293-102">CControlledCA función)</span><span class="sxs-lookup"><span data-stu-id="cf293-102">CControlledCA function</span></span>

<span data-ttu-id="cf293-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cf293-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cf293-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf293-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf293-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="cf293-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="cf293-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="cf293-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="cf293-107">El modificador `CA` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="cf293-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="cf293-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="cf293-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="cf293-109">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de> CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="cf293-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="cf293-110">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="cf293-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="cf293-111">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) => de la [unidad](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="cf293-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="cf293-112">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="cf293-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cf293-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="cf293-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cf293-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="cf293-114">'T</span></span>

<span data-ttu-id="cf293-115">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="cf293-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf293-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf293-116">See Also</span></span>

- [<span data-ttu-id="cf293-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="cf293-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)