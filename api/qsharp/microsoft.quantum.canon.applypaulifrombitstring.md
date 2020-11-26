---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Operación ApplyPauliFromBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: cf4c99ec5134fac788cdd4c8a057258790152a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209067"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="a21a1-102">Operación ApplyPauliFromBitString</span><span class="sxs-lookup"><span data-stu-id="a21a1-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="a21a1-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a21a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a21a1-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a21a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a21a1-105">Aplica un operador Pauli en cada qubit de una matriz si el bit correspondiente de una matriz booleana coincide con una entrada determinada.</span><span class="sxs-lookup"><span data-stu-id="a21a1-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a21a1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a21a1-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="a21a1-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a21a1-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a21a1-108">Operador Pauli que se va a aplicar a `qubits[idx]` Where `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="a21a1-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="a21a1-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a21a1-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a21a1-110">aplicar Pauli si el bit es este valor</span><span class="sxs-lookup"><span data-stu-id="a21a1-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="a21a1-111">bits: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a21a1-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a21a1-112">Registro booleano que especifica el qubit correspondiente en el que `qubits` se debe operar</span><span class="sxs-lookup"><span data-stu-id="a21a1-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a21a1-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a21a1-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a21a1-114">Registro de Quantum en el que se aplicará de forma selectiva el operador Pauli especificado</span><span class="sxs-lookup"><span data-stu-id="a21a1-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="a21a1-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a21a1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a21a1-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a21a1-116">Remarks</span></span>

<span data-ttu-id="a21a1-117">La matriz booleana y el registro Quantum deben tener la misma longitud.</span><span class="sxs-lookup"><span data-stu-id="a21a1-117">The Boolean array and the quantum register must be of equal length.</span></span>