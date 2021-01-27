---
uid: Microsoft.Quantum.Bitwise.Parity
title: Función de paridad
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Parity
qsharp.summary: Returns the bitwise PARITY of an integer (1 if its binary representation contains odd number of ones and 0 otherwise).
ms.openlocfilehash: b34ef36b0336ec1dea7fdbd878c6d695b38d623e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842125"
---
# <a name="parity-function"></a><span data-ttu-id="76900-102">Función de paridad</span><span class="sxs-lookup"><span data-stu-id="76900-102">Parity function</span></span>

<span data-ttu-id="76900-103">Espacio de nombres: [Microsoft. Quantum. bit a bit](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="76900-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="76900-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="76900-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="76900-105">Devuelve la paridad bit a bit de un entero (1 Si su representación binaria contiene un número impar de unos y 0 de lo contrario).</span><span class="sxs-lookup"><span data-stu-id="76900-105">Returns the bitwise PARITY of an integer (1 if its binary representation contains odd number of ones and 0 otherwise).</span></span>

```qsharp
function Parity (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="76900-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="76900-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="76900-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76900-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="76900-108">Salida: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76900-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="76900-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76900-109">Example</span></span>

```qsharp
let a = 248;
let x = Parity(a); // x : Int = 1.
```