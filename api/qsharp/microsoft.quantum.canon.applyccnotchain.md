---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: Operación ApplyCCNOTChain
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: e4f38e9bb54839076b817f6e61e96ca6a550576b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729693"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="3c4e2-102">Operación ApplyCCNOTChain</span><span class="sxs-lookup"><span data-stu-id="3c4e2-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="3c4e2-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c4e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c4e2-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c4e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c4e2-105">Implementa una cascada de puertas de CCNOT controladas en los bits correspondientes de dos registros qubit, actuando en el siguiente qubit de uno de los registros.</span><span class="sxs-lookup"><span data-stu-id="3c4e2-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="3c4e2-106">A partir de qubits en la posición 0 en ambos registros como controles, CCNOT se aplica a qubit en la posición 1 del registro de destino y, a continuación, se controla mediante la qubits en la posición 1 que actúa en el qubit en la posición 2 del registro de destino, etc., que termina con una acción en el qubit de destino en la posición `Length(nQubits)-1` .</span><span class="sxs-lookup"><span data-stu-id="3c4e2-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3c4e2-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="3c4e2-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="3c4e2-108">registro: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3c4e2-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3c4e2-109">Registro de qubit, solo se usa para los controles.</span><span class="sxs-lookup"><span data-stu-id="3c4e2-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="3c4e2-110">destinos: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3c4e2-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3c4e2-111">Registro qubit, se usa para los controles y como destino.</span><span class="sxs-lookup"><span data-stu-id="3c4e2-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c4e2-112">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c4e2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3c4e2-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c4e2-113">Remarks</span></span>

<span data-ttu-id="3c4e2-114">El registro de qubit de destino debe tener una qubit más que el otro registro.</span><span class="sxs-lookup"><span data-stu-id="3c4e2-114">The target qubit register must have one qubit more than the other register.</span></span>