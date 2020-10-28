---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729789"
---
# <a name="zbits-function"></a><span data-ttu-id="1dffb-102">ZBits función)</span><span class="sxs-lookup"><span data-stu-id="1dffb-102">ZBits function</span></span>

<span data-ttu-id="1dffb-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="1dffb-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="1dffb-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1dffb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1dffb-105">Devuelve un entero que representa los bits Z de una matriz de operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="1dffb-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="1dffb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1dffb-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="1dffb-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="1dffb-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="1dffb-108">Matriz de operadores Pauli que se va a representar como un entero.</span><span class="sxs-lookup"><span data-stu-id="1dffb-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="1dffb-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1dffb-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1dffb-110">Entero $x $ con la representación binaria $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, donde $p _I = $0 si `paulis[i]` es `PauliI` o `PauliX` y donde $p _I = $1 si `paulis[i]` es `PauliY` o `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="1dffb-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1dffb-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1dffb-111">Remarks</span></span>

<span data-ttu-id="1dffb-112">La función producirá una excepción si la longitud de la `paulis` matriz es mayor que 63.</span><span class="sxs-lookup"><span data-stu-id="1dffb-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dffb-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1dffb-113">See Also</span></span>

- [<span data-ttu-id="1dffb-114">Microsoft. Quantum. bit a bit. XBits</span><span class="sxs-lookup"><span data-stu-id="1dffb-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)