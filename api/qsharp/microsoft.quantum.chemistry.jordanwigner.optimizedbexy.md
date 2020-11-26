---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: Operación OptimizedBEXY
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 3530e62671e16cfb5500c56c8e5e477dbb56e67e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224860"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="d2c87-102">Operación OptimizedBEXY</span><span class="sxs-lookup"><span data-stu-id="d2c87-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="d2c87-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="d2c87-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="d2c87-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d2c87-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="d2c87-105">$U unitario $ que aplica la cadena de Pauli en $ (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 $ on qubits $0.. p $ condicionada en un índice $z \en \{ 0, 1 \} $ y $p $.</span><span class="sxs-lookup"><span data-stu-id="d2c87-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="d2c87-106">Es decir, $ $ \begin{align} U\ket {z} \ les {p} \ les {\ PSI} = \ket{z}\ket{p} (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d2c87-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d2c87-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d2c87-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="d2c87-108">pauliBasis: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d2c87-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d2c87-109">Cuando este qubit se encuentra en el estado $ \ket {0} $, se aplica $X $.</span><span class="sxs-lookup"><span data-stu-id="d2c87-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="d2c87-110">Cuando se encuentra en el estado $ \ket {1} $, se aplica $Y $.</span><span class="sxs-lookup"><span data-stu-id="d2c87-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="d2c87-111">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d2c87-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d2c87-112">El estado $ \ket{p} $ de este registro determina el qubit en el que se aplica $X $ o $Y $.</span><span class="sxs-lookup"><span data-stu-id="d2c87-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="d2c87-113">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d2c87-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d2c87-114">Registro de qubits en el que se aplican los operadores de Pauli.</span><span class="sxs-lookup"><span data-stu-id="d2c87-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d2c87-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2c87-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="d2c87-116">Referencias</span><span class="sxs-lookup"><span data-stu-id="d2c87-116">References</span></span>

- <span data-ttu-id="d2c87-117">Codifique los espectros electrónicos en los circuitos Quantum con la complejidad T lineal Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pálido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="d2c87-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>