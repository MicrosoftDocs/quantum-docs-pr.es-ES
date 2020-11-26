---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: Operación Mayús
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 356689baa6d47b7b93a393f3672991bb589f6921
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222769"
---
# <a name="maj-operation"></a><span data-ttu-id="e3939-102">Operación Mayús</span><span class="sxs-lookup"><span data-stu-id="e3939-102">MAJ operation</span></span>

<span data-ttu-id="e3939-103">Espacio de nombres: [Microsoft. Quantum. aritmético](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e3939-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e3939-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3939-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3939-105">Esto aplica la operación de mayoría local a 3 qubits.</span><span class="sxs-lookup"><span data-stu-id="e3939-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e3939-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3939-106">Description</span></span>

<span data-ttu-id="e3939-107">Si denotamos el estado de la qubit de destino como $ \ket{z} $ y los Estados de entrada de la qubits de entrada como $ \ket{x} $ y $ \ket{y} $, esta operación realiza la siguiente transformación: $ \ket{XYZ} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)} $.</span><span class="sxs-lookup"><span data-stu-id="e3939-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="e3939-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e3939-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="e3939-109">input0: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e3939-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e3939-110">La primera entrada qubit.</span><span class="sxs-lookup"><span data-stu-id="e3939-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="e3939-111">entrada1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e3939-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e3939-112">La segunda entrada qubit.</span><span class="sxs-lookup"><span data-stu-id="e3939-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e3939-113">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e3939-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e3939-114">Un qubit en el que se aplicará la función mayoritario.</span><span class="sxs-lookup"><span data-stu-id="e3939-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3939-115">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3939-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

