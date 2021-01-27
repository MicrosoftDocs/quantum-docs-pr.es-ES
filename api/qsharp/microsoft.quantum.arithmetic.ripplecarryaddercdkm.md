---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Operación RippleCarryAdderCDKM
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: df9b62b649af532a4202aacc3e8dd4613eb8665d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846361"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="b01f8-102">Operación RippleCarryAdderCDKM</span><span class="sxs-lookup"><span data-stu-id="b01f8-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="b01f8-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b01f8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b01f8-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b01f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b01f8-105">Agregación reversible, en contexto, de dos enteros.</span><span class="sxs-lookup"><span data-stu-id="b01f8-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b01f8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b01f8-106">Description</span></span>

<span data-ttu-id="b01f8-107">Dados dos $n enteros de $ bits codificados en registros de LittleEndian `xs` y `ys` , y un transporte de qubit, la operación calcula la suma de los dos enteros donde se conservan los bits $n $ menos significativos del resultado en `ys` y el bit de transporte es XORed a qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="b01f8-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="b01f8-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b01f8-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="b01f8-109">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b01f8-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b01f8-110">LittleEndian qubit registra la codificación del primer entero sumando.</span><span class="sxs-lookup"><span data-stu-id="b01f8-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="b01f8-111">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b01f8-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b01f8-112">LittleEndian qubit registra la codificación del segundo entero sumando, se modifica para contener los n bits menos significativos de la suma.</span><span class="sxs-lookup"><span data-stu-id="b01f8-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="b01f8-113">transporte: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b01f8-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b01f8-114">Transportar qubit, es XORed con el bit más significativo de la suma.</span><span class="sxs-lookup"><span data-stu-id="b01f8-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b01f8-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b01f8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b01f8-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b01f8-116">Remarks</span></span>

<span data-ttu-id="b01f8-117">Esta operación tiene la misma funcionalidad que RippleCarryAdderD, pero solo usa un qubit auxiliar en lugar de $n $.</span><span class="sxs-lookup"><span data-stu-id="b01f8-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="b01f8-118">Referencias</span><span class="sxs-lookup"><span data-stu-id="b01f8-118">References</span></span>

- <span data-ttu-id="b01f8-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "un nuevo circuito de adición del transporte de onda de Quantum", 2004.</span><span class="sxs-lookup"><span data-stu-id="b01f8-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1