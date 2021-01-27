---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: ddaace8df6e4c47c4affe2eeffb8d8ce31f37327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845246"
---
# <a name="xbits-function"></a><span data-ttu-id="dfa0d-102">XBits función)</span><span class="sxs-lookup"><span data-stu-id="dfa0d-102">XBits function</span></span>

<span data-ttu-id="dfa0d-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="dfa0d-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="dfa0d-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="dfa0d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="dfa0d-105">Devuelve un entero que representa los bits X de una matriz de operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="dfa0d-105">Returns an integer representing the X bits of an array of Pauli operators.</span></span>

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="dfa0d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dfa0d-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="dfa0d-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="dfa0d-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="dfa0d-108">Matriz de operadores Pauli que se va a representar como un entero.</span><span class="sxs-lookup"><span data-stu-id="dfa0d-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="dfa0d-109">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dfa0d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dfa0d-110">Entero $x $ con la representación binaria $ (p_ {62} \, p_ {61} \, \dots \, p_0) $, donde $p _I = $0 si `paulis[i]` es `PauliI` o `PauliZ` y donde $p _I = $1 si `paulis[i]` es `PauliX` o `PauliY` .</span><span class="sxs-lookup"><span data-stu-id="dfa0d-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliZ` and where $p_i = 1$ if `paulis[i]` is `PauliX` or `PauliY`.</span></span>

## <a name="remarks"></a><span data-ttu-id="dfa0d-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dfa0d-111">Remarks</span></span>

<span data-ttu-id="dfa0d-112">La función producirá una excepción si la longitud de la `paulis` matriz es mayor que 63.</span><span class="sxs-lookup"><span data-stu-id="dfa0d-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfa0d-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dfa0d-113">See Also</span></span>

- [<span data-ttu-id="dfa0d-114">Microsoft. Quantum. bit a bit. ZBits</span><span class="sxs-lookup"><span data-stu-id="dfa0d-114">Microsoft.Quantum.Bitwise.ZBits</span></span>](xref:Microsoft.Quantum.Bitwise.ZBits)