---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Operación cuadradai
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221868"
---
# <a name="squarei-operation"></a><span data-ttu-id="1565b-102">Operación cuadradai</span><span class="sxs-lookup"><span data-stu-id="1565b-102">SquareI operation</span></span>

<span data-ttu-id="1565b-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1565b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1565b-104">Paquete: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="1565b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="1565b-105">Calcula el cuadrado del entero `xs` en `result` , que debe ser cero inicialmente.</span><span class="sxs-lookup"><span data-stu-id="1565b-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1565b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1565b-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="1565b-107">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1565b-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1565b-108">$n un número de bits a Square (LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1565b-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="1565b-109">resultado: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1565b-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1565b-110">el resultado de $2N $-bit (LittleEndian) debe estar en el estado $ \ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="1565b-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1565b-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1565b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1565b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1565b-112">Remarks</span></span>

<span data-ttu-id="1565b-113">Utiliza un enfoque estándar de desplazamiento y adición para calcular el cuadrado.</span><span class="sxs-lookup"><span data-stu-id="1565b-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="1565b-114">Guarda $n-$1 qubits en comparación con la solución de reenvío directo que primero copia los XS antes de aplicar un multiplicador normal y, a continuación, deshacer la operación de copia.</span><span class="sxs-lookup"><span data-stu-id="1565b-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>