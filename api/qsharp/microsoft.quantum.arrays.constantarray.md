---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846224"
---
# <a name="constantarray-function"></a><span data-ttu-id="0c4ec-102">ConstantArray función)</span><span class="sxs-lookup"><span data-stu-id="0c4ec-102">ConstantArray function</span></span>

<span data-ttu-id="0c4ec-103">Espacio de nombres: [Microsoft. Quantum. matrices](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0c4ec-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0c4ec-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0c4ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0c4ec-105">Crea una matriz de longitud determinada con todos los elementos iguales al valor especificado.</span><span class="sxs-lookup"><span data-stu-id="0c4ec-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0c4ec-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="0c4ec-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="0c4ec-107">longitud: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0c4ec-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0c4ec-108">Longitud de la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="0c4ec-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="0c4ec-109">valor: ' t</span><span class="sxs-lookup"><span data-stu-id="0c4ec-109">value : 'T</span></span>

<span data-ttu-id="0c4ec-110">Valor de cada elemento de la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="0c4ec-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="0c4ec-111">Salida: ' t []</span><span class="sxs-lookup"><span data-stu-id="0c4ec-111">Output : 'T[]</span></span>

<span data-ttu-id="0c4ec-112">Nueva matriz de longitud `length` , de modo que todos los elementos son `value` .</span><span class="sxs-lookup"><span data-stu-id="0c4ec-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0c4ec-113">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="0c4ec-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0c4ec-114">Traslada</span><span class="sxs-lookup"><span data-stu-id="0c4ec-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="0c4ec-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c4ec-115">Example</span></span>

<span data-ttu-id="0c4ec-116">En el código siguiente se crea una matriz de 3 valores booleanos, cada uno de ellos igual a `true` :</span><span class="sxs-lookup"><span data-stu-id="0c4ec-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```