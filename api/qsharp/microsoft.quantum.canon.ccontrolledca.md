---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: cc1a783dfbf97afae50f4b42e66cba2b2a2ec833
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207435"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="c0763-102">CControlledCA función)</span><span class="sxs-lookup"><span data-stu-id="c0763-102">CControlledCA function</span></span>

<span data-ttu-id="c0763-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c0763-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c0763-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0763-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0763-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="c0763-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="c0763-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="c0763-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="c0763-107">El modificador `CA` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="c0763-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="c0763-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="c0763-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="c0763-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c0763-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c0763-110">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="c0763-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj--ctl"></a><span data-ttu-id="c0763-111">Output: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c0763-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c0763-112">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="c0763-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c0763-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="c0763-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c0763-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="c0763-114">'T</span></span>

<span data-ttu-id="c0763-115">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="c0763-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0763-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0763-116">See Also</span></span>

- [<span data-ttu-id="c0763-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="c0763-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)