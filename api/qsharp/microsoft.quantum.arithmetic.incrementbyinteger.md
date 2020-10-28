---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: Operación IncrementByInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731509"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="8b2bd-102">Operación IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="8b2bd-102">IncrementByInteger operation</span></span>

<span data-ttu-id="8b2bd-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8b2bd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8b2bd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b2bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b2bd-105">Incrementa un registro de Quantum sin signo mediante un entero clásico, usando giros de fase.</span><span class="sxs-lookup"><span data-stu-id="8b2bd-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="8b2bd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b2bd-106">Description</span></span>

<span data-ttu-id="8b2bd-107">Supongamos que `target` codifica un entero sin signo $x $ en una codificación Little-endian y que `increment` es igual a $a $.</span><span class="sxs-lookup"><span data-stu-id="8b2bd-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="8b2bd-108">A continuación, esta operación implementa la unitario $ \ket{x} \mapsto \ket{x + a} $, donde la adición se realiza en módulo $2 ^ n $, donde $n = \texttt{Length (Target!)} $.</span><span class="sxs-lookup"><span data-stu-id="8b2bd-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="8b2bd-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="8b2bd-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="8b2bd-110">incremento: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b2bd-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8b2bd-111">Entero por el que `target` se incrementa.</span><span class="sxs-lookup"><span data-stu-id="8b2bd-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="8b2bd-112">destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8b2bd-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8b2bd-113">Un registro de Quantum codifica un entero sin signo mediante la codificación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="8b2bd-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b2bd-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b2bd-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

