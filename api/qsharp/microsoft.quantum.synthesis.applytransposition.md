---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Operación ApplyTransposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855583"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="16fb7-102">Operación ApplyTransposition</span><span class="sxs-lookup"><span data-stu-id="16fb7-102">ApplyTransposition operation</span></span>

<span data-ttu-id="16fb7-103">Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="16fb7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="16fb7-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16fb7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="16fb7-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="16fb7-105">Description</span></span>

<span data-ttu-id="16fb7-106">Esta operación intercambia la amplitud en el índice `a` con la amplitud en `b` el índice en el vector de estado dado de `register` longitud $n $.</span><span class="sxs-lookup"><span data-stu-id="16fb7-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="16fb7-107">Si es `a` igual `b` a, el vector de estado no cambia.</span><span class="sxs-lookup"><span data-stu-id="16fb7-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="16fb7-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="16fb7-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="16fb7-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="16fb7-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="16fb7-110">Primer índice (debe ser un valor comprendido entre 0 y $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="16fb7-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="16fb7-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="16fb7-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="16fb7-112">Segundo índice (debe ser un valor comprendido entre 0 y $2 ^ n-$1)</span><span class="sxs-lookup"><span data-stu-id="16fb7-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="16fb7-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="16fb7-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="16fb7-114">Una lista de $n $ qubits a la que se aplica la transposición.</span><span class="sxs-lookup"><span data-stu-id="16fb7-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="16fb7-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16fb7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="16fb7-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16fb7-116">Example</span></span>

<span data-ttu-id="16fb7-117">Prepare una superposición uniforme de los Estados de número $ | 1 \ Rangle $, $ | 2 \ Rangle $ y $ | 3 \ Rangle $ en 2 qubits.</span><span class="sxs-lookup"><span data-stu-id="16fb7-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```