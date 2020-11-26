---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: cb72ca5b3dab99b9ee8a994ba9fde46e0eae5594
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207520"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="26eda-102">CControlledA función)</span><span class="sxs-lookup"><span data-stu-id="26eda-102">CControlledA function</span></span>

<span data-ttu-id="26eda-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="26eda-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="26eda-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26eda-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26eda-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="26eda-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="26eda-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="26eda-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="26eda-107">El modificador `A` indica que la operación es adjointable.</span><span class="sxs-lookup"><span data-stu-id="26eda-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="26eda-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="26eda-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="26eda-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="26eda-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="26eda-110">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="26eda-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj"></a><span data-ttu-id="26eda-111">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="26eda-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="26eda-112">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="26eda-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="26eda-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="26eda-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="26eda-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="26eda-114">'T</span></span>

<span data-ttu-id="26eda-115">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="26eda-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="26eda-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26eda-116">See Also</span></span>

- [<span data-ttu-id="26eda-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="26eda-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)