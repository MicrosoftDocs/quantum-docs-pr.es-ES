---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operación ApplyXorInPlace
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731700"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="031fd-102">Operación ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="031fd-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="031fd-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="031fd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="031fd-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="031fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="031fd-105">Aplica una operación XOR bit a bit entre un entero clásico y un entero representado por un registro de qubits.</span><span class="sxs-lookup"><span data-stu-id="031fd-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="031fd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="031fd-106">Description</span></span>

<span data-ttu-id="031fd-107">Aplica `X` operaciones a qubits en un registro Little-Endian basado en 1 bit en un entero.</span><span class="sxs-lookup"><span data-stu-id="031fd-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="031fd-108">Vamos `value` a indicar mediante un y dejar que y sea un entero sin signo codificado en `target` , `InPlaceXorLE` realiza una operación proporcionada por la siguiente asignación: $ \ket{y}\rightarrow \ket{y\oplus a} $, donde $ \oplus $ es el operador OR exclusivo bit a bit.</span><span class="sxs-lookup"><span data-stu-id="031fd-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="031fd-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="031fd-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="031fd-110">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="031fd-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="031fd-111">Entero que se supone que no es negativo.</span><span class="sxs-lookup"><span data-stu-id="031fd-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="031fd-112">destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="031fd-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="031fd-113">Un registro de Quantum que se usa para almacenar `value` en la codificación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="031fd-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="031fd-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="031fd-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

