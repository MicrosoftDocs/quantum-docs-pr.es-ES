---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728877"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="84b8f-102">CControlledA función)</span><span class="sxs-lookup"><span data-stu-id="84b8f-102">CControlledA function</span></span>

<span data-ttu-id="84b8f-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="84b8f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="84b8f-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84b8f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84b8f-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="84b8f-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="84b8f-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="84b8f-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="84b8f-107">El modificador `A` indica que la operación es adjointable.</span><span class="sxs-lookup"><span data-stu-id="84b8f-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="84b8f-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="84b8f-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="84b8f-109">OP: ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84b8f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="84b8f-110">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="84b8f-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="84b8f-111">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) => ADJ de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84b8f-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="84b8f-112">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="84b8f-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="84b8f-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="84b8f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84b8f-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="84b8f-114">'T</span></span>

<span data-ttu-id="84b8f-115">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="84b8f-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="84b8f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84b8f-116">See Also</span></span>

- [<span data-ttu-id="84b8f-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="84b8f-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)