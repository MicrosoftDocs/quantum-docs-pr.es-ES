---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: Operación AllowAtMostNQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727365"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="d0915-102">Operación AllowAtMostNQubits</span><span class="sxs-lookup"><span data-stu-id="d0915-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="d0915-103">Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d0915-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d0915-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0915-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0915-105">Entre una llamada a esta operación y su método contiguo, se declara que como máximo un número determinado de qubits adicionales se asignan con instrucciones using.</span><span class="sxs-lookup"><span data-stu-id="d0915-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d0915-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d0915-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="d0915-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d0915-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d0915-108">Número máximo de qubits que se pueden asignar.</span><span class="sxs-lookup"><span data-stu-id="d0915-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="d0915-109">Message: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d0915-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d0915-110">Mensaje que se va a mostrar cuando se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="d0915-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d0915-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d0915-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d0915-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d0915-112">Remarks</span></span>

<span data-ttu-id="d0915-113">Esta operación se puede reemplazar por una no operativa en destinos que no la admitan.</span><span class="sxs-lookup"><span data-stu-id="d0915-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>