---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732621"
---
# <a name="quantumrom-function"></a><span data-ttu-id="8d2b7-102">QuantumROM función)</span><span class="sxs-lookup"><span data-stu-id="8d2b7-102">QuantumROM function</span></span>

<span data-ttu-id="8d2b7-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8d2b7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8d2b7-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d2b7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d2b7-105">Usa la técnica de ROM Quantum para representar una matriz de densidad determinada.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="8d2b7-106">Dada una lista de $N $ coeficientes $ \ alpha_j $, se devuelve un valor de unitario $U $ que usa la técnica Quantum-ROM para preparar una aproximación $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ de la depuración de la matriz de densidad $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="8d2b7-107">En esta aproximación, el error $ \epsilon $ es tal que $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ y $ \| \tilde\rho-\rho \| \le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="8d2b7-108">En otras palabras, $ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ les {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{Garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="8d2b7-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8d2b7-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="8d2b7-110">Entrada</span><span class="sxs-lookup"><span data-stu-id="8d2b7-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="8d2b7-111">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8d2b7-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8d2b7-112">El error de destino $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="8d2b7-113">coeficientes: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8d2b7-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8d2b7-114">Matriz de $N $ coeficientes que especifican la probabilidad de Estados de base.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="8d2b7-115">Los números negativos $-\ alpha_j $ se tratarán como positivos $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="8d2b7-116">Salida: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL)</span><span class="sxs-lookup"><span data-stu-id="8d2b7-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="8d2b7-117">Primer parámetro</span><span class="sxs-lookup"><span data-stu-id="8d2b7-117">First parameter</span></span>

<span data-ttu-id="8d2b7-118">Una tupla `(x,(y,z))` donde `x = y + z` es el número total de qubits asignados, `y` es el número de qubits para el `LittleEndian` registro y `z` es el número de qubits de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="8d2b7-119">Segundo parámetro</span><span class="sxs-lookup"><span data-stu-id="8d2b7-119">Second parameter</span></span>

<span data-ttu-id="8d2b7-120">La norma $ \ sum_j | \ alpha_j | $ de la matriz de coeficientes.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="8d2b7-121">Tercer parámetro</span><span class="sxs-lookup"><span data-stu-id="8d2b7-121">Third parameter</span></span>

<span data-ttu-id="8d2b7-122">La $U unitario $.</span><span class="sxs-lookup"><span data-stu-id="8d2b7-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="8d2b7-123">Referencias</span><span class="sxs-lookup"><span data-stu-id="8d2b7-123">References</span></span>

- <span data-ttu-id="8d2b7-124">Codifique los espectros electrónicos en los circuitos Quantum con la complejidad T lineal Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pálido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="8d2b7-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>