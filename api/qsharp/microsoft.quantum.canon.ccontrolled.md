---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728882"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="fac5a-102">CControlled función)</span><span class="sxs-lookup"><span data-stu-id="fac5a-102">CControlled function</span></span>

<span data-ttu-id="fac5a-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fac5a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fac5a-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fac5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fac5a-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="fac5a-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="fac5a-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="fac5a-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="fac5a-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="fac5a-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="fac5a-108">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="fac5a-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fac5a-109">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="fac5a-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="fac5a-110">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="fac5a-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fac5a-111">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="fac5a-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fac5a-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="fac5a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fac5a-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="fac5a-113">'T</span></span>

<span data-ttu-id="fac5a-114">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="fac5a-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="fac5a-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fac5a-115">See Also</span></span>

- [<span data-ttu-id="fac5a-116">Microsoft. Quantum. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="fac5a-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="fac5a-117">Microsoft. Quantum. Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="fac5a-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="fac5a-118">Microsoft. Quantum. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="fac5a-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)