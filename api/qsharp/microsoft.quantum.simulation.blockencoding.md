---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: Tipo definido por el usuario BlockEncoding
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 75fdbf13cf07d906982d4a611d1d25b3e29db2cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225438"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="9e889-102">Tipo definido por el usuario BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="9e889-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="9e889-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9e889-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9e889-104">Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e889-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e889-105">Representa una unidad en la que un operador arbitrario de interés se codifica en el bloque superior izquierdo.</span><span class="sxs-lookup"><span data-stu-id="9e889-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="9e889-106">Es decir, `BlockEncoding` es una unidad $U $ donde un operador arbitrario $H $ de interés que actúa en el registro del sistema `s` se codifica en el bloque superior izquierdo correspondiente al estado auxiliar $ \ket {0} _a $.</span><span class="sxs-lookup"><span data-stu-id="9e889-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="9e889-107">Es decir:</span><span class="sxs-lookup"><span data-stu-id="9e889-107">That is,</span></span>

<span data-ttu-id="9e889-108">$ $ \begin{align} (\bra {0} _a \otimes I_s) U (\ket {0} _a \otimes I_s) = H \end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="9e889-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

