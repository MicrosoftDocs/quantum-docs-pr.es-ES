---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operación cuadradai
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730461"
---
# <a name="squarei-operation"></a><span data-ttu-id="158e4-102">Operación cuadradai</span><span class="sxs-lookup"><span data-stu-id="158e4-102">SquareI operation</span></span>

<span data-ttu-id="158e4-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="158e4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="158e4-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="158e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="158e4-105">Calcula el cuadrado del entero `xs` en `result` , que debe ser cero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="158e4-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="158e4-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="158e4-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="158e4-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="158e4-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="158e4-108">$n un número de bits a Square (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="158e4-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="158e4-109">resultado: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="158e4-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="158e4-110">el resultado de $2N $-bit (LittleEndian) debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="158e4-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="158e4-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="158e4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="158e4-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="158e4-112">Remarks</span></span>

<span data-ttu-id="158e4-113">Utiliza un enfoque estándar de desplazamiento y adición para calcular el cuadrado.</span><span class="sxs-lookup"><span data-stu-id="158e4-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="158e4-114">Guarda $n-$1 qubits en comparación con la solución de reenvío directo que primero copia los XS antes de aplicar un multiplicador normal y, a continuación, deshacer la operación de copia.</span><span class="sxs-lookup"><span data-stu-id="158e4-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>