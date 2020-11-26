---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Operación ApplyToLittleEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: 1194ac369d2d474330357d26dd22709e9c68dd6e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226492"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="63f3c-102">Operación ApplyToLittleEndian</span><span class="sxs-lookup"><span data-stu-id="63f3c-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="63f3c-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="63f3c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="63f3c-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63f3c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63f3c-105">Aplica una operación a la qubits subyacente que conforman un registro Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="63f3c-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="63f3c-106">Esta operación se marca como interna, ya que un registro Little-Endian está pensado para ser "opaco", de modo que esto solo es un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="63f3c-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="63f3c-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="63f3c-107">Input</span></span>

### <a name="bareop--qubit--unit--is-adj--ctl"></a><span data-ttu-id="63f3c-108">bareOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="63f3c-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="63f3c-109">registro: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="63f3c-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="63f3c-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63f3c-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

