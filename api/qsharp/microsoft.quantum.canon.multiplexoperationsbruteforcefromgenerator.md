---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: Operación MultiplexOperationsBruteForceFromGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2a9bb083b121745bd556aac692d5dc85ffec3791
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728552"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="54ef6-102">Operación MultiplexOperationsBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="54ef6-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="54ef6-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="54ef6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="54ef6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54ef6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54ef6-105">Aplica la operación de unitarios controlada por multiplicación $U $ que aplica una $V unitario _j $ cuando está controlada por el estado de n-qubit número $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="54ef6-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="54ef6-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="54ef6-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="54ef6-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="54ef6-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="54ef6-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> ' t => de [unidad](xref:microsoft.quantum.lang-ref.unit) ajustable + CTL)</span><span class="sxs-lookup"><span data-stu-id="54ef6-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="54ef6-109">Una tupla en la que el primer elemento `Int` es el número de unitaries $N $ y el segundo elemento `(Int -> ('T => () is Adj + Ctl))` es una función que toma un entero $j $ in $ [0, N-1] $ y genera la operación unitario $V _J $.</span><span class="sxs-lookup"><span data-stu-id="54ef6-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="54ef6-110">Índice: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="54ef6-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="54ef6-111">$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="54ef6-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="54ef6-112">destino: ' t</span><span class="sxs-lookup"><span data-stu-id="54ef6-112">target : 'T</span></span>

<span data-ttu-id="54ef6-113">Registro qubit genérico en el que $V _j $ actúa.</span><span class="sxs-lookup"><span data-stu-id="54ef6-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54ef6-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54ef6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="54ef6-115">Parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="54ef6-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="54ef6-116">Traslada</span><span class="sxs-lookup"><span data-stu-id="54ef6-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="54ef6-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="54ef6-117">Remarks</span></span>

<span data-ttu-id="54ef6-118">`coefficients` se rellenará con elementos Identity si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="54ef6-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="54ef6-119">Esta versión se implementa directamente mediante el bucle a través de los operadores unitarios controlados por n.</span><span class="sxs-lookup"><span data-stu-id="54ef6-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>