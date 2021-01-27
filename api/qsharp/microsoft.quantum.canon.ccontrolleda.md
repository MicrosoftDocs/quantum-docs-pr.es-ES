---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 823d80182621691f4fa6f42246b3d671f3adfc3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840991"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="bffcd-102">CControlledA función)</span><span class="sxs-lookup"><span data-stu-id="bffcd-102">CControlledA function</span></span>

<span data-ttu-id="bffcd-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bffcd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bffcd-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bffcd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bffcd-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="bffcd-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="bffcd-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="bffcd-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="bffcd-107">El modificador `A` indica que la operación es adjointable.</span><span class="sxs-lookup"><span data-stu-id="bffcd-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="bffcd-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="bffcd-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="bffcd-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es ADJ</span><span class="sxs-lookup"><span data-stu-id="bffcd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="bffcd-110">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="bffcd-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj"></a><span data-ttu-id="bffcd-111">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ</span><span class="sxs-lookup"><span data-stu-id="bffcd-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="bffcd-112">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="bffcd-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bffcd-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="bffcd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bffcd-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="bffcd-114">'T</span></span>

<span data-ttu-id="bffcd-115">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="bffcd-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bffcd-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bffcd-116">See Also</span></span>

- [<span data-ttu-id="bffcd-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="bffcd-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)