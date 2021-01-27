---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841010"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="40b0c-102">CControlled función)</span><span class="sxs-lookup"><span data-stu-id="40b0c-102">CControlled function</span></span>

<span data-ttu-id="40b0c-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="40b0c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="40b0c-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40b0c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40b0c-105">Dada una operación OP, devuelve una nueva operación que aplica el operador OP si un bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="40b0c-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="40b0c-106">Si es `false` , no sucede nada.</span><span class="sxs-lookup"><span data-stu-id="40b0c-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="40b0c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="40b0c-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="40b0c-108">OP: ' t = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="40b0c-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="40b0c-109">Operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="40b0c-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="40b0c-110">Salida: ([bool](xref:microsoft.quantum.lang-ref.bool), ' t) = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="40b0c-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="40b0c-111">Nueva operación que es operativa si el bit de control clásico es true.</span><span class="sxs-lookup"><span data-stu-id="40b0c-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="40b0c-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="40b0c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="40b0c-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="40b0c-113">'T</span></span>

<span data-ttu-id="40b0c-114">Tipo de entrada de la operación que se va a aplicar condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="40b0c-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="40b0c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40b0c-115">See Also</span></span>

- [<span data-ttu-id="40b0c-116">Microsoft. Quantum. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="40b0c-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="40b0c-117">Microsoft. Quantum. Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="40b0c-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="40b0c-118">Microsoft. Quantum. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="40b0c-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)