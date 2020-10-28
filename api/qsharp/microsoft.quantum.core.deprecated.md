---
uid: Microsoft.Quantum.Core.Deprecated
title: Tipo definido por el usuario en desuso
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727460"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="25502-102">Tipo definido por el usuario en desuso</span><span class="sxs-lookup"><span data-stu-id="25502-102">Deprecated user defined type</span></span>

<span data-ttu-id="25502-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="25502-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="25502-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25502-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25502-105">Atributo reconocido por el compilador que se usa para marcar un tipo o que se puede llamar como desusado.</span><span class="sxs-lookup"><span data-stu-id="25502-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="25502-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="25502-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="25502-107">NewName: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="25502-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="25502-108">Nombre completo del tipo o al que se puede llamar para usar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="25502-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="25502-109">Se establece en la cadena vacía si un tipo o al que se puede llamar se ha dejado de usar sin sustitución.</span><span class="sxs-lookup"><span data-stu-id="25502-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>