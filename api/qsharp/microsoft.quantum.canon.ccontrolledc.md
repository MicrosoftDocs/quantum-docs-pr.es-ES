---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: a10c8f0f835fe7cbb8f2d89d521a548169613c0a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840978"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="f7a97-102">CControlledC función)</span><span class="sxs-lookup"><span data-stu-id="f7a97-102">CControlledC function</span></span>

<span data-ttu-id="f7a97-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7a97-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7a97-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7a97-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7a97-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="f7a97-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="f7a97-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="f7a97-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="f7a97-107">El modificador `C` indica que la operación es controlable.</span><span class="sxs-lookup"><span data-stu-id="f7a97-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="f7a97-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="f7a97-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f7a97-109">OP: ' t => [unidad](xref:microsoft.quantum.lang-ref.unit)  es CTL</span><span class="sxs-lookup"><span data-stu-id="f7a97-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f7a97-110">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f7a97-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-ctl"></a><span data-ttu-id="f7a97-111">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es CTL</span><span class="sxs-lookup"><span data-stu-id="f7a97-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f7a97-112">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="f7a97-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f7a97-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="f7a97-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7a97-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="f7a97-114">'T</span></span>

<span data-ttu-id="f7a97-115">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="f7a97-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7a97-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7a97-116">See Also</span></span>

- [<span data-ttu-id="f7a97-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="f7a97-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)