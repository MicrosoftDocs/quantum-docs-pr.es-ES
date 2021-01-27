---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Operación ApplyToLittleEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: a8c765d4b8f5d2f09cf68b7140e31c9114643733
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856983"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="fc63e-102">Operación ApplyToLittleEndian</span><span class="sxs-lookup"><span data-stu-id="fc63e-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="fc63e-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="fc63e-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="fc63e-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc63e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fc63e-105">Aplica una operación a la qubits subyacente que conforman un registro Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="fc63e-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="fc63e-106">Esta operación se marca como interna, ya que un registro Little-Endian está pensado para ser "opaco", de modo que esto solo es un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="fc63e-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fc63e-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="fc63e-107">Input</span></span>

### <a name="bareop--qubit--unit--is-adj--ctl"></a><span data-ttu-id="fc63e-108">bareOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="fc63e-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="fc63e-109">registro: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fc63e-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="fc63e-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc63e-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

