---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209764"
---
# <a name="xbits-function"></a><span data-ttu-id="9f3b2-102">XBits función)</span><span class="sxs-lookup"><span data-stu-id="9f3b2-102">XBits function</span></span>

<span data-ttu-id="9f3b2-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="9f3b2-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="9f3b2-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9f3b2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9f3b2-105">Devuelve un entero que representa los bits X de una matriz de operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="9f3b2-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="9f3b2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9f3b2-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="9f3b2-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="9f3b2-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="9f3b2-108">Matriz de operadores Pauli que se va a representar como un entero.</span><span class="sxs-lookup"><span data-stu-id="9f3b2-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="9f3b2-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f3b2-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f3b2-110">Entero $x $ con la representación binaria $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, donde $p _I = $0 si `paulis[i]` es `PauliI` o `PauliZ` y donde $p _I = $1 si `paulis[i]` es `PauliX` o `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="9f3b2-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f3b2-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9f3b2-111">Remarks</span></span>

<span data-ttu-id="9f3b2-112">La función producirá una excepción si la longitud de la `paulis` matriz es mayor que 63.</span><span class="sxs-lookup"><span data-stu-id="9f3b2-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f3b2-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f3b2-113">See Also</span></span>

- [<span data-ttu-id="9f3b2-114">Microsoft. Quantum. bit a bit. ZBits</span><span class="sxs-lookup"><span data-stu-id="9f3b2-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)