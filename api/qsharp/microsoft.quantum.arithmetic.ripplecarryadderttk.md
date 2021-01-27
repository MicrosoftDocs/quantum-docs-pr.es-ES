---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: Operación RippleCarryAdderTTK
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: cf7f8ed10de2243627a001b770a4d29ff7345f30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842945"
---
# <a name="ripplecarryadderttk-operation"></a><span data-ttu-id="77165-102">Operación RippleCarryAdderTTK</span><span class="sxs-lookup"><span data-stu-id="77165-102">RippleCarryAdderTTK operation</span></span>

<span data-ttu-id="77165-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="77165-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="77165-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77165-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77165-105">Agregación reversible, en contexto, de dos enteros.</span><span class="sxs-lookup"><span data-stu-id="77165-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="77165-106">Dados dos $n enteros de $ bits codificados en registros de LittleEndian `xs` y `ys` , y un transporte de qubit, la operación calcula la suma de los dos enteros donde se conservan los bits $n $ menos significativos del resultado en `ys` y el bit de transporte es XORed a qubit `carry` .</span><span class="sxs-lookup"><span data-stu-id="77165-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="77165-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="77165-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="77165-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="77165-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="77165-109">LittleEndian qubit registra la codificación del primer entero sumando.</span><span class="sxs-lookup"><span data-stu-id="77165-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="77165-110">calendario: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="77165-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="77165-111">LittleEndian qubit registra la codificación del segundo entero sumando, se modifica para contener los bits $n $ menos significativos de la suma.</span><span class="sxs-lookup"><span data-stu-id="77165-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="77165-112">transporte: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="77165-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="77165-113">Transportar qubit, es XORed con el bit más significativo de la suma.</span><span class="sxs-lookup"><span data-stu-id="77165-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="77165-114">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77165-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="77165-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="77165-115">Remarks</span></span>

<span data-ttu-id="77165-116">Esta operación tiene la misma funcionalidad que RippleCarryAdderD y, RippleCarryAdderCDKM, pero no usa ningún qubits de ancilla.</span><span class="sxs-lookup"><span data-stu-id="77165-116">This operation has the same functionality as RippleCarryAdderD and, RippleCarryAdderCDKM but does not use any ancilla qubits.</span></span>

## <a name="references"></a><span data-ttu-id="77165-117">Referencias</span><span class="sxs-lookup"><span data-stu-id="77165-117">References</span></span>

- <span data-ttu-id="77165-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Additions de Quantum y ramificación sin límite", información de Quantum y cálculo, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="77165-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530