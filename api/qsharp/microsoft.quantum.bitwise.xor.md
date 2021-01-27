---
uid: Microsoft.Quantum.Bitwise.Xor
title: XOR (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Xor
qsharp.summary: Returns the bitwise exclusive-OR (XOR) of two integers. This performs the same computation as the built-in `^^^` operator.
ms.openlocfilehash: ac31ba973ff06424dbd16168dac14a79b2691b3f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842078"
---
# <a name="xor-function"></a><span data-ttu-id="99e12-102">XOR (función)</span><span class="sxs-lookup"><span data-stu-id="99e12-102">Xor function</span></span>

<span data-ttu-id="99e12-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="99e12-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="99e12-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="99e12-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="99e12-105">Devuelve la operación OR exclusiva bit a bit (XOR) de dos enteros.</span><span class="sxs-lookup"><span data-stu-id="99e12-105">Returns the bitwise exclusive-OR (XOR) of two integers.</span></span>
<span data-ttu-id="99e12-106">Esto realiza el mismo cálculo que el `^^^` operador integrado.</span><span class="sxs-lookup"><span data-stu-id="99e12-106">This performs the same computation as the built-in `^^^` operator.</span></span>

```qsharp
function Xor (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="99e12-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="99e12-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="99e12-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99e12-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="99e12-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99e12-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="99e12-110">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="99e12-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="99e12-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99e12-111">Example</span></span>

```qsharp
let a = 248;       //                 11111000₂
let b = 63;        //                 00111111₂
let x = Xor(a, b); // x : Int = 199 = 11000111₂.
```

## <a name="remarks"></a><span data-ttu-id="99e12-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99e12-112">Remarks</span></span>

<span data-ttu-id="99e12-113">Vea el [operador de C# ^](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="99e12-113">See the [C# ^ Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) for more details.</span></span>