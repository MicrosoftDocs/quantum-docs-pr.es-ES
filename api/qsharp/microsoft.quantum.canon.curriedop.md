---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840762"
---
# <a name="curriedop-function"></a><span data-ttu-id="bd108-102">CurriedOp función)</span><span class="sxs-lookup"><span data-stu-id="bd108-102">CurriedOp function</span></span>

<span data-ttu-id="bd108-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd108-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd108-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd108-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd108-105">Devuelve una versión currificada de una operación con dos entradas.</span><span class="sxs-lookup"><span data-stu-id="bd108-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="bd108-106">Es decir, dada una operación con dos entradas, esta función aplica isomorphism de la $f (x, y) \equiv f (x) $ para devolver una operación de una entrada que devuelve una operación de una entrada.</span><span class="sxs-lookup"><span data-stu-id="bd108-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="bd108-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="bd108-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="bd108-108">OP: (' t, ' U) = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="bd108-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bd108-109">Operación cuya entrada es un par.</span><span class="sxs-lookup"><span data-stu-id="bd108-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="bd108-110">Salida: ' t-> ' U = [unidad](xref:microsoft.quantum.lang-ref.unit) de></span><span class="sxs-lookup"><span data-stu-id="bd108-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bd108-111">Una operación que acepta el primer elemento de un par y devuelve una operación que acepta como entrada el segundo elemento de la entrada de la operación original.</span><span class="sxs-lookup"><span data-stu-id="bd108-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd108-112">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="bd108-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd108-113">Traslada</span><span class="sxs-lookup"><span data-stu-id="bd108-113">'T</span></span>

<span data-ttu-id="bd108-114">Tipo del primer componente de una función definida en pares.</span><span class="sxs-lookup"><span data-stu-id="bd108-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="bd108-115">' U</span><span class="sxs-lookup"><span data-stu-id="bd108-115">'U</span></span>

<span data-ttu-id="bd108-116">Tipo del segundo componente de una función definida en pares.</span><span class="sxs-lookup"><span data-stu-id="bd108-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd108-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bd108-117">Remarks</span></span>

<span data-ttu-id="bd108-118">Los siguientes son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="bd108-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```