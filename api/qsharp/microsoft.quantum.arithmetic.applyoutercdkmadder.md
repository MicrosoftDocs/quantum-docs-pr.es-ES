---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: Operación ApplyOuterCDKMAdder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731813"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="e7f24-102">Operación ApplyOuterCDKMAdder</span><span class="sxs-lookup"><span data-stu-id="e7f24-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="e7f24-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e7f24-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e7f24-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e7f24-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e7f24-105">Operación de transporte de rizo reversible y en contexto que se usa en la operación de suma de enteros RippleCarryAdderCDKM a continuación.</span><span class="sxs-lookup"><span data-stu-id="e7f24-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="e7f24-106">Dados dos registros de qubit `xs` y `ys` de la misma longitud, la operación aplica una secuencia de transporte de rizo de CNOT y puertas de CCNOT con qubits en `xs` y `ys` como los controles y Qubits `xs` como destinos.</span><span class="sxs-lookup"><span data-stu-id="e7f24-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e7f24-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="e7f24-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e7f24-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e7f24-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e7f24-109">Primer registro de qubit, que contiene controles y destinos.</span><span class="sxs-lookup"><span data-stu-id="e7f24-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e7f24-110">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e7f24-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e7f24-111">Segundo registro de qubit, que contribuye a los controles.</span><span class="sxs-lookup"><span data-stu-id="e7f24-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="e7f24-112">ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e7f24-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e7f24-113">Ancilla qubit usado en RippleCarryAdderCDKM pasado a esta operación.</span><span class="sxs-lookup"><span data-stu-id="e7f24-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7f24-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7f24-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e7f24-115">Referencias</span><span class="sxs-lookup"><span data-stu-id="e7f24-115">References</span></span>

- <span data-ttu-id="e7f24-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "un nuevo circuito de adición del transporte de onda de Quantum", 2004.</span><span class="sxs-lookup"><span data-stu-id="e7f24-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1