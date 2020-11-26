---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Operación ApplyPauli
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: 7f42d9cab2f80f8f826ad1268b050134f0540cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218230"
---
# <a name="applypauli-operation"></a><span data-ttu-id="dc582-102">Operación ApplyPauli</span><span class="sxs-lookup"><span data-stu-id="dc582-102">ApplyPauli operation</span></span>

<span data-ttu-id="dc582-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc582-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc582-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc582-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc582-105">Dado un operador Pauli de varios qubit, aplica la operación correspondiente a un registro.</span><span class="sxs-lookup"><span data-stu-id="dc582-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dc582-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="dc582-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="dc582-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="dc582-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="dc582-108">Un operador qubit de Pauli que se representa como una matriz de operadores Pauli de qubit único.</span><span class="sxs-lookup"><span data-stu-id="dc582-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="dc582-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dc582-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dc582-110">Regístrese para aplicar la operación Pauli especificada en.</span><span class="sxs-lookup"><span data-stu-id="dc582-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc582-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc582-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

