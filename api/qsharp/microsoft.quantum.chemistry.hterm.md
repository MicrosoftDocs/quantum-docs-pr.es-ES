---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Tipo definido por el usuario HTerm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 744668a4fe96ee00fe2f7991f4e1f05eea19d417
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851785"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="88d23-102">Tipo definido por el usuario HTerm</span><span class="sxs-lookup"><span data-stu-id="88d23-102">HTerm user defined type</span></span>

<span data-ttu-id="88d23-103">Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="88d23-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="88d23-104">Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="88d23-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="88d23-105">Formato de los datos pasados de C# a Q # para representar un término de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="88d23-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="88d23-106">El significado de los datos representados viene determinado por el algoritmo que lo recibe.</span><span class="sxs-lookup"><span data-stu-id="88d23-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

