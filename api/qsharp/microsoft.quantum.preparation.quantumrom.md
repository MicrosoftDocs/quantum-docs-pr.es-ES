---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 64ed9aed7c9d9a4a689c5926f3cd085a2521c4db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856813"
---
# <a name="quantumrom-function"></a><span data-ttu-id="3774a-102">QuantumROM función)</span><span class="sxs-lookup"><span data-stu-id="3774a-102">QuantumROM function</span></span>

<span data-ttu-id="3774a-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3774a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3774a-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3774a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="3774a-105">QuantumROM está en desuso.</span><span class="sxs-lookup"><span data-stu-id="3774a-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="3774a-106">Use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3774a-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="3774a-107">Usa la técnica de ROM Quantum para representar una matriz de densidad determinada.</span><span class="sxs-lookup"><span data-stu-id="3774a-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="3774a-108">Dada una lista de $N $ coeficientes $ \ alpha_j $, se devuelve un valor de unitario $U $ que usa la técnica Quantum-ROM para preparar una aproximación $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ de la depuración de la matriz de densidad $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="3774a-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="3774a-109">En esta aproximación, el error $ \epsilon $ es tal que $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ y $ \| \tilde\rho-\rho \| \le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="3774a-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="3774a-110">En otras palabras, $ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ les {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{Garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="3774a-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="3774a-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3774a-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="3774a-112">Entrada</span><span class="sxs-lookup"><span data-stu-id="3774a-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="3774a-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3774a-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3774a-114">El error de destino $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="3774a-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="3774a-115">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3774a-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3774a-116">Matriz de $N $ coeficientes que especifican la probabilidad de Estados de base.</span><span class="sxs-lookup"><span data-stu-id="3774a-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="3774a-117">Los números negativos $-\ alpha_j $ se tratarán como positivos $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="3774a-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="3774a-118">Salida: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="3774a-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="3774a-119">Primer parámetro</span><span class="sxs-lookup"><span data-stu-id="3774a-119">First parameter</span></span>

<span data-ttu-id="3774a-120">Una tupla `(x,(y,z))` donde `x = y + z` es el número total de qubits asignados, `y` es el número de qubits para el `LittleEndian` registro y `z` es el número de qubits de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3774a-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="3774a-121">Segundo parámetro</span><span class="sxs-lookup"><span data-stu-id="3774a-121">Second parameter</span></span>

<span data-ttu-id="3774a-122">La norma $ \ sum_j | \ alpha_j | $ de la matriz de coeficientes.</span><span class="sxs-lookup"><span data-stu-id="3774a-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="3774a-123">Tercer parámetro</span><span class="sxs-lookup"><span data-stu-id="3774a-123">Third parameter</span></span>

<span data-ttu-id="3774a-124">La $U unitario $.</span><span class="sxs-lookup"><span data-stu-id="3774a-124">The unitary $U$.</span></span>

## <a name="example"></a><span data-ttu-id="3774a-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3774a-125">Example</span></span>

<span data-ttu-id="3774a-126">El siguiente fragmento de código prepara una purificación del estado $3 $-qubit $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, donde $ \vec\alpha = (1.0, 2.0, 3.0, 4.0, 5.0) $ y el error es `1e-3` ;</span><span class="sxs-lookup"><span data-stu-id="3774a-126">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0,2.0,3.0,4.0,5.0)$, and the error is `1e-3`;</span></span>

```qsharp
let coefficients = [1.0,2.0,3.0,4.0,5.0];
let targetError = 1e-3;
let ((nTotalQubits, (nIndexQubits, nGarbageQubits)), oneNorm, op) = QuantumROM(targetError, coefficients);
using (indexRegister = Qubit[nIndexQubits]) {
    using (garbageRegister = Qubit[nGarbageQubits]) {
        op(LittleEndian(indexRegister), garbageRegister);
    }
}
```

## <a name="references"></a><span data-ttu-id="3774a-127">Referencias</span><span class="sxs-lookup"><span data-stu-id="3774a-127">References</span></span>

- <span data-ttu-id="3774a-128">Codifique los espectros electrónicos en los circuitos Quantum con la complejidad T lineal Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pálido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="3774a-128">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>