---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Operación ApplyPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729405"
---
# <a name="applypauli-operation"></a><span data-ttu-id="ecfc6-102">Operación ApplyPauli</span><span class="sxs-lookup"><span data-stu-id="ecfc6-102">ApplyPauli operation</span></span>

<span data-ttu-id="ecfc6-103">Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ecfc6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ecfc6-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ecfc6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ecfc6-105">Dado un operador Pauli de varios qubit, aplica la operación correspondiente a un registro.</span><span class="sxs-lookup"><span data-stu-id="ecfc6-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ecfc6-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ecfc6-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="ecfc6-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ecfc6-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ecfc6-108">Un operador qubit de Pauli que se representa como una matriz de operadores Pauli de qubit único.</span><span class="sxs-lookup"><span data-stu-id="ecfc6-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ecfc6-109">destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ecfc6-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ecfc6-110">Regístrese para aplicar la operación Pauli especificada en.</span><span class="sxs-lookup"><span data-stu-id="ecfc6-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ecfc6-111">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ecfc6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

