---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector operación
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727407"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="09876-102">_assertEqualOnBasisVector operación</span><span class="sxs-lookup"><span data-stu-id="09876-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="09876-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="09876-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="09876-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09876-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09876-105">Comprueba si el resultado de aplicar dos operaciones `givenU` y `expectedU` a un estado de base es el mismo.</span><span class="sxs-lookup"><span data-stu-id="09876-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="09876-106">El estado de base se describe mediante el `basis` parámetro.</span><span class="sxs-lookup"><span data-stu-id="09876-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="09876-107">Consulte <xref:microsoft.quantum.extensions.fliptobasis> función para obtener más detalles sobre esta descripción.</span><span class="sxs-lookup"><span data-stu-id="09876-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="09876-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="09876-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="09876-109">base: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="09876-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="09876-110">Estado de base especificado por un identificador de estado de base de un solo qubit (0 <= ID <= 3) para cada $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="09876-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="09876-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidad](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="09876-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="09876-112">Operación en $n $ qubits que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="09876-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="09876-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09876-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="09876-114">Operación de referencia en $n $ qubits con la que se va a comparar givenU.</span><span class="sxs-lookup"><span data-stu-id="09876-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09876-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09876-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

