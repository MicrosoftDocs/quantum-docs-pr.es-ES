---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operación KnillDistill
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853118"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="e7a66-102">Operación KnillDistill</span><span class="sxs-lookup"><span data-stu-id="e7a66-102">KnillDistill operation</span></span>

<span data-ttu-id="e7a66-103">Espacio de nombres: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e7a66-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e7a66-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7a66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7a66-105">Implementa el algoritmo de destilación de estado mágico de Knill.</span><span class="sxs-lookup"><span data-stu-id="e7a66-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="e7a66-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7a66-106">Description</span></span>

<span data-ttu-id="e7a66-107">Dadas 15 copias aproximadas de un estado mágico $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} \end{align}, $ $ produce una copia de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="e7a66-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="e7a66-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="e7a66-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="e7a66-109">roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e7a66-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e7a66-110">Un registro de quince qubits que contiene copias aproximadas de un estado mágico.</span><span class="sxs-lookup"><span data-stu-id="e7a66-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="e7a66-111">La siguiente aplicación de este procedimiento de destilación contendrá `roughMagic[0]` una copia de mayor calidad y el resto del registro se restablecerá al estado $ \ket{00\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="e7a66-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e7a66-112">Salida: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e7a66-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e7a66-113">Si `true` es, el procedimiento se realizó correctamente y se debe aceptar la copia de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="e7a66-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="e7a66-114">Si `false` es, se produce un error en el procedimiento, y el estado del registro se debe considerar sin definir.</span><span class="sxs-lookup"><span data-stu-id="e7a66-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7a66-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7a66-115">Remarks</span></span>

<span data-ttu-id="e7a66-116">Seguimos el algoritmo de Knill.</span><span class="sxs-lookup"><span data-stu-id="e7a66-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="e7a66-117">Sin embargo, la implementación actual está lejos de ser óptima, ya que utiliza demasiados qubits.</span><span class="sxs-lookup"><span data-stu-id="e7a66-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="e7a66-118">Los Estados mágicos se insertan en esta rutina, en cuyo caso hay mejores protocolos.</span><span class="sxs-lookup"><span data-stu-id="e7a66-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="e7a66-119">Referencias</span><span class="sxs-lookup"><span data-stu-id="e7a66-119">References</span></span>

- [<span data-ttu-id="e7a66-120">Knill</span><span class="sxs-lookup"><span data-stu-id="e7a66-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)