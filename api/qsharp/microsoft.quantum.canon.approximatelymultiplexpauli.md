---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: Operación ApproximatelyMultiplexPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: c91937d9e82a2a1514d81529adb35a5f804a0e13
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728978"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="0f1f3-102">Operación ApproximatelyMultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="0f1f3-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="0f1f3-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f1f3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f1f3-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f1f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f1f3-105">Aplica una rotación Pauli condicionada en una matriz de qubits, truncando ángulos de rotación pequeños según una tolerancia determinada.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="0f1f3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f1f3-106">Description</span></span>

<span data-ttu-id="0f1f3-107">Esto aplica una operación de unitarios controlada multiplicación que realiza rotaciones por ángulo $ \ theta_j $ sobre el operador Pauli de un solo qubit $P $ cuando lo controla el $n $-qubit Number $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="0f1f3-108">En concreto, la acción de esta operación está representada por la unitario</span><span class="sxs-lookup"><span data-stu-id="0f1f3-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="0f1f3-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="0f1f3-110">\end{align}</span><span class="sxs-lookup"><span data-stu-id="0f1f3-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="0f1f3-111">Entrada</span><span class="sxs-lookup"><span data-stu-id="0f1f3-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="0f1f3-112">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0f1f3-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0f1f3-113">Tolerancia por debajo de la cual se truncan los coeficientes pequeños.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="0f1f3-114">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0f1f3-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0f1f3-115">Matriz de hasta $2 ^ n $ coeficientes $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="0f1f3-116">El coeficiente de $j $ TH indexa el número $ \ket{j} $ codificado en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="0f1f3-117">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="0f1f3-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="0f1f3-118">Operador Pauli $P $ que determina el eje de giro.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="0f1f3-119">control: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f1f3-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f1f3-120">$n registro de control $-qubit que codifica los Estados de número $ \ket{j} $ en formato Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0f1f3-121">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0f1f3-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0f1f3-122">Registro de qubit único que gira $e ^ {i P \ theta_j} $.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f1f3-123">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f1f3-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0f1f3-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f1f3-124">Remarks</span></span>

<span data-ttu-id="0f1f3-125">`coefficients` se rellenará con los elementos $ \ theta_j = $0,0 si se especifican menos de $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="0f1f3-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f1f3-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f1f3-126">See Also</span></span>

- [<span data-ttu-id="0f1f3-127">Microsoft. Quantum. Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="0f1f3-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)