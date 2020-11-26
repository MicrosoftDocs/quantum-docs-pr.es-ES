---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Operación SelectZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 08abe3f465432bf98f35090c59fb4d952c3b4882
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224724"
---
# <a name="selectz-operation"></a><span data-ttu-id="4f118-102">Operación SelectZ</span><span class="sxs-lookup"><span data-stu-id="4f118-102">SelectZ operation</span></span>

<span data-ttu-id="4f118-103">Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4f118-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4f118-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4f118-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4f118-105">Una $U unitario $ que aplica la puerta de $Z $ Pauli en un qubits $p $ condicionado a un estado de índice $ \ket{p} $.</span><span class="sxs-lookup"><span data-stu-id="4f118-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="4f118-106">Es decir, $ $ \begin{align} U\ket {p} \ les {\ PSI} = \ket{p}Z \_ p\ket {\ PSI} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="4f118-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4f118-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="4f118-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="4f118-108">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4f118-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4f118-109">El estado $ \ket{p} $ de este registro determina el qubit en el que se aplica $Z $.</span><span class="sxs-lookup"><span data-stu-id="4f118-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="4f118-110">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4f118-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4f118-111">Registro de qubits en el que se aplican los operadores de Pauli.</span><span class="sxs-lookup"><span data-stu-id="4f118-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f118-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f118-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

