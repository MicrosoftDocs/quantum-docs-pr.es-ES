---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operación ApplyXorInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843466"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="c8861-102">Operación ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="c8861-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="c8861-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c8861-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c8861-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8861-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8861-105">Aplica una operación XOR bit a bit entre un entero clásico y un entero representado por un registro de qubits.</span><span class="sxs-lookup"><span data-stu-id="c8861-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c8861-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8861-106">Description</span></span>

<span data-ttu-id="c8861-107">Aplica `X` operaciones a qubits en un registro Little-Endian basado en 1 bit en un entero.</span><span class="sxs-lookup"><span data-stu-id="c8861-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="c8861-108">Vamos `value` a indicar mediante un y dejar que y sea un entero sin signo codificado en `target` , `InPlaceXorLE` realiza una operación proporcionada por la siguiente asignación: $ \ket{y}\rightarrow \ket{y\oplus a} $, donde $ \oplus $ es el operador OR exclusivo bit a bit.</span><span class="sxs-lookup"><span data-stu-id="c8861-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="c8861-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8861-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="c8861-110">valor: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8861-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8861-111">Entero que se supone que no es negativo.</span><span class="sxs-lookup"><span data-stu-id="c8861-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="c8861-112">destino: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c8861-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c8861-113">Un registro de Quantum que se usa para almacenar `value` en la codificación Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="c8861-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8861-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8861-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

