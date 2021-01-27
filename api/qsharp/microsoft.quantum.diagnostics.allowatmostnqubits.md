---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operación AllowAtMostNQubits
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830909"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="dc0a5-102">Operación AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="dc0a5-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="dc0a5-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="dc0a5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="dc0a5-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc0a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc0a5-105">Entre una llamada a esta operación y su método contiguo, se declara que como máximo un número determinado de qubits adicionales se asignan con instrucciones using.</span><span class="sxs-lookup"><span data-stu-id="dc0a5-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="dc0a5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dc0a5-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="dc0a5-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dc0a5-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dc0a5-108">Número máximo de qubits que se pueden asignar.</span><span class="sxs-lookup"><span data-stu-id="dc0a5-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="dc0a5-109">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="dc0a5-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="dc0a5-110">Mensaje que se va a mostrar cuando se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="dc0a5-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc0a5-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc0a5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="dc0a5-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc0a5-112">Example</span></span>

<span data-ttu-id="dc0a5-113">El siguiente fragmento de código producirá un error cuando se ejecute en equipos que admiten este diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="dc0a5-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="dc0a5-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dc0a5-114">Remarks</span></span>

<span data-ttu-id="dc0a5-115">Esta operación se puede reemplazar por una no operativa en destinos que no la admitan.</span><span class="sxs-lookup"><span data-stu-id="dc0a5-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>