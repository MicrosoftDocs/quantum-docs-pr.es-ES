---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: Operación AssertOperationsEqualReferenced
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: a3e8791321b4f2ca1885dffeb92c7b13e5491a32
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727323"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="2b17b-102">Operación AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="2b17b-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="2b17b-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2b17b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2b17b-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b17b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b17b-105">Dadas dos operaciones, garantiza que actúan de forma idéntica para todos los Estados de entrada.</span><span class="sxs-lookup"><span data-stu-id="2b17b-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="2b17b-106">Esta aserción se implementa mediante Choi – Jamiołkowski isomorphism para reducir la aserción a una de una aserción de estado de qubit en dos registros indebidos.</span><span class="sxs-lookup"><span data-stu-id="2b17b-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="2b17b-107">Por lo tanto, esta operación solo necesita una llamada a cada operación que se está probando, pero requiere que se asignen dos veces el número de qubits.</span><span class="sxs-lookup"><span data-stu-id="2b17b-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="2b17b-108">Esta aserción se puede usar para garantizar, por ejemplo, que una versión optimizada de una operación actúa de manera idéntica a su implementación de Naive o que una operación que actúa en un intervalo de entradas que no son de Quantum coincide con casos conocidos.</span><span class="sxs-lookup"><span data-stu-id="2b17b-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="2b17b-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="2b17b-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2b17b-110">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b17b-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b17b-111">Número de qubits que se van a pasar a cada operación.</span><span class="sxs-lookup"><span data-stu-id="2b17b-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="2b17b-112">real: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="2b17b-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2b17b-113">Operación que se va a probar.</span><span class="sxs-lookup"><span data-stu-id="2b17b-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="2b17b-114">se esperaba: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ADJ de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b17b-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="2b17b-115">Operación que define el comportamiento esperado para la operación sometida a prueba.</span><span class="sxs-lookup"><span data-stu-id="2b17b-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b17b-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b17b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2b17b-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2b17b-117">Remarks</span></span>

<span data-ttu-id="2b17b-118">Esta operación requiere que la operación que modela el comportamiento esperado sea adjointable, de modo que el inverso pueda realizarse solo en el registro de destino.</span><span class="sxs-lookup"><span data-stu-id="2b17b-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="2b17b-119">Formalmente, se puede especificar una operación de transposición, lo que relaja este requisito, pero la operación de transposición no se realiza en general físicamente para operaciones de Quantum arbitrarias y, por tanto, no se incluye aquí como opción.</span><span class="sxs-lookup"><span data-stu-id="2b17b-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>