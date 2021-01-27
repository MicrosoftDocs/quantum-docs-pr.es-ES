---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 740461ee17bdda281a6bd8572a15d27b17be9535
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840952"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="787f9-102">CControlledCA función)</span><span class="sxs-lookup"><span data-stu-id="787f9-102">CControlledCA function</span></span>

<span data-ttu-id="787f9-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="787f9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="787f9-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="787f9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="787f9-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="787f9-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="787f9-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="787f9-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="787f9-107">El modificador `CA` indica que la operación es controlable y adjointable.</span><span class="sxs-lookup"><span data-stu-id="787f9-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="787f9-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="787f9-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="787f9-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="787f9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="787f9-110">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="787f9-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj--ctl"></a><span data-ttu-id="787f9-111">Output: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="787f9-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="787f9-112">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="787f9-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="787f9-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="787f9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="787f9-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="787f9-114">'T</span></span>

<span data-ttu-id="787f9-115">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="787f9-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="787f9-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="787f9-116">See Also</span></span>

- [<span data-ttu-id="787f9-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="787f9-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)