---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728876"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="32927-102">CControlledC función)</span><span class="sxs-lookup"><span data-stu-id="32927-102">CControlledC function</span></span>

<span data-ttu-id="32927-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="32927-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="32927-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="32927-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="32927-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="32927-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="32927-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="32927-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="32927-107">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="32927-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="32927-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="32927-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="32927-109">OP: ' t => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32927-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="32927-110">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="32927-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="32927-111">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) => CTL de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32927-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="32927-112">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="32927-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="32927-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="32927-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="32927-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="32927-114">'T</span></span>

<span data-ttu-id="32927-115">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="32927-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="32927-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32927-116">See Also</span></span>

- [<span data-ttu-id="32927-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="32927-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)