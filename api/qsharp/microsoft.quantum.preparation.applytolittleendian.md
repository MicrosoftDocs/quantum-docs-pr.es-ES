---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Operación ApplyToLittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: d94a9969a3f827d594946ab8ca6cd4672da7ef7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733277"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="d648d-102">Operación ApplyToLittleEndian</span><span class="sxs-lookup"><span data-stu-id="d648d-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="d648d-103">Espacio de nombres: [Microsoft. Quantum. preparación](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d648d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d648d-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d648d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d648d-105">Aplica una operación a la qubits subyacente que conforman un registro Little-Endian.</span><span class="sxs-lookup"><span data-stu-id="d648d-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="d648d-106">Esta operación se marca como interna, ya que un registro Little-Endian está pensado para ser "opaco", de modo que esto solo es un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="d648d-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d648d-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="d648d-107">Input</span></span>

### <a name="bareop--qubit--unit-adj--ctl"></a><span data-ttu-id="d648d-108">bareOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => de [unidad](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="d648d-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="d648d-109">registro: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d648d-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="d648d-110">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d648d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

