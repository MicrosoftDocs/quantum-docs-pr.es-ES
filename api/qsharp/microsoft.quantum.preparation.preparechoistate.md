---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Operación PrepareChoiState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: cb34078c09f8c28b5b9bbda1bae6936d13ffcc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854399"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="b1892-102">Operación PrepareChoiState</span><span class="sxs-lookup"><span data-stu-id="b1892-102">PrepareChoiState operation</span></span>

<span data-ttu-id="b1892-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="b1892-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="b1892-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1892-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1892-105">Prepara el estado Choi – Jamiołkowski para una operación determinada en determinados registros de referencia y de destino.</span><span class="sxs-lookup"><span data-stu-id="b1892-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b1892-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b1892-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="b1892-107">OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="b1892-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b1892-108">Operación $ \Lambda $ cuya Choi – Jamiołkowski State $J (\Lambda)/2 ^ N $ se va a preparar, donde $N $ es el número de qubits en el que `op` actúa.</span><span class="sxs-lookup"><span data-stu-id="b1892-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="b1892-109">Referencia: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b1892-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b1892-110">Un registro de qubits a partir del estado $ \ket{00\cdots 0} $ que se va a usar como referencia para la acción de `op` .</span><span class="sxs-lookup"><span data-stu-id="b1892-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b1892-111">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b1892-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b1892-112">Un registro de qubits inicialmente en el estado $ \ket{00\cdots 0} $ en el que `op` se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="b1892-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1892-113">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1892-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b1892-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b1892-114">Remarks</span></span>

<span data-ttu-id="b1892-115">Choi – Jamiłkowski State $J (\Lambda) $ de un proceso Quantum se define como $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ Where $ | X\rangle \! \rangle $ es la *vectorización* de una matriz $X $ en la Convención de apilamiento de columnas.</span><span class="sxs-lookup"><span data-stu-id="b1892-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="b1892-116">El aprendizaje de una descripción clásica de este estado proporciona información completa sobre el efecto de $ \Lambda $ que actúa en Estados de entrada arbitrarios y forma la base del *proceso de Quantum Tomography*.</span><span class="sxs-lookup"><span data-stu-id="b1892-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1892-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1892-117">See Also</span></span>

- [<span data-ttu-id="b1892-118">Microsoft. Quantum. preparación. PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="b1892-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="b1892-119">Microsoft. Quantum. preparación. PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="b1892-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="b1892-120">Microsoft. Quantum. preparación. PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="b1892-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)