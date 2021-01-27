---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Operación AssertQubitIsInStateWithinTolerance
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829784"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="15f6d-102">Operación AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="15f6d-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="15f6d-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="15f6d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="15f6d-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="15f6d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="15f6d-105">Valida que qubit en el estado esperado.</span><span class="sxs-lookup"><span data-stu-id="15f6d-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="15f6d-106">`expected` representa un vector complejo, $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.</span><span class="sxs-lookup"><span data-stu-id="15f6d-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="15f6d-107">El primer elemento de las tuplas que representa cada una de $a $, $b $ es la parte real del número complejo, mientras que la segunda es la parte imaginaria.</span><span class="sxs-lookup"><span data-stu-id="15f6d-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="15f6d-108">El último argumento define la tolerancia con la que se realiza la aserción.</span><span class="sxs-lookup"><span data-stu-id="15f6d-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="15f6d-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="15f6d-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="15f6d-110">esperado: ([complejo](xref:Microsoft.Quantum.Math.Complex),[complejo](xref:Microsoft.Quantum.Math.Complex))</span><span class="sxs-lookup"><span data-stu-id="15f6d-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="15f6d-111">Se esperaban las amplitudes complejas de $ \ket {0} $ y $ \ket {1} $, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="15f6d-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="15f6d-112">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="15f6d-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="15f6d-113">Qubit cuyo estado se va a declarar.</span><span class="sxs-lookup"><span data-stu-id="15f6d-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="15f6d-114">Tenga en cuenta que se supone que este qubit se puede separar de otros qubits asignados y no está insuficiente.</span><span class="sxs-lookup"><span data-stu-id="15f6d-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="15f6d-115">tolerancia: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="15f6d-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="15f6d-116">Tolerancia aditiva mediante la cual se permite que las amplitudes reales se desvíen de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="15f6d-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="15f6d-117">Vea la sección Comentarios a continuación para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="15f6d-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15f6d-118">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15f6d-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="15f6d-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15f6d-119">Example</span></span>

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="15f6d-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15f6d-120">Remarks</span></span>

<span data-ttu-id="15f6d-121">El siguiente código de Mathematica se puede usar para comprobar las expresiones de mi, mx, My, MZ:</span><span class="sxs-lookup"><span data-stu-id="15f6d-121">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="15f6d-122">La tolerancia es la $L \_ {\infty} $ distance entre 3 vectores reales (x ₂, x ₃, x ₄) definido por $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 y + x \_ 4 Z $ y Vector real (y ₂, y ₃, y ₄) definidos por p = y ₁ I + y ₂ x + y ₃ y + y ₄ Z, donde p es la matriz de densidad que corresponde al estado del registro.</span><span class="sxs-lookup"><span data-stu-id="15f6d-122">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="15f6d-123">Esto solo se aplica en la suposición de que TR (p) y TR (| ψ ⟩ ⟨ ψ |) son 1 (por ejemplo, x ₁ = 1/2, y ₁ = 1/2).</span><span class="sxs-lookup"><span data-stu-id="15f6d-123">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="15f6d-124">Si no es así, la función garantiza que la distancia l ∞ entre (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) y (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) es menor que el parámetro Tolerance.</span><span class="sxs-lookup"><span data-stu-id="15f6d-124">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>