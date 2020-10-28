---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Operación CarryOutCoreCDKM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731637"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="4b2ea-102">Operación CarryOutCoreCDKM</span><span class="sxs-lookup"><span data-stu-id="4b2ea-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="4b2ea-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4b2ea-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4b2ea-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b2ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b2ea-105">La operación básica en RippleCarryAdderCDKM, que se usa con la operación de ApplyOuterCDKMAdder anterior, es decir, conjugado con esta operación para obtener la operación interna de RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="4b2ea-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="4b2ea-106">Esta operación calcula el qubit de ejecución y aplica una secuencia de no puertas en parte de la entrada `ys` .</span><span class="sxs-lookup"><span data-stu-id="4b2ea-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="4b2ea-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="4b2ea-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="4b2ea-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4b2ea-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4b2ea-109">Primer registro de qubit.</span><span class="sxs-lookup"><span data-stu-id="4b2ea-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="4b2ea-110">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4b2ea-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4b2ea-111">Segundo registro de qubit.</span><span class="sxs-lookup"><span data-stu-id="4b2ea-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="4b2ea-112">ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4b2ea-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4b2ea-113">Ancilla qubit usado en RippleCarryAdderCDKM pasado a esta operación.</span><span class="sxs-lookup"><span data-stu-id="4b2ea-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="4b2ea-114">transporte: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4b2ea-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4b2ea-115">Realice qubit en la operación RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="4b2ea-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b2ea-116">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b2ea-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="4b2ea-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="4b2ea-117">References</span></span>

- <span data-ttu-id="4b2ea-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "un nuevo circuito de adición del transporte de onda de Quantum", 2004.</span><span class="sxs-lookup"><span data-stu-id="4b2ea-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1