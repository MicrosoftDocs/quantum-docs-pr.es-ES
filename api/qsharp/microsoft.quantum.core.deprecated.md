---
uid: Microsoft.Quantum.Core.Deprecated
title: Tipo definido por el usuario en desuso
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224095"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="5cbf1-102">Tipo definido por el usuario en desuso</span><span class="sxs-lookup"><span data-stu-id="5cbf1-102">Deprecated user defined type</span></span>

<span data-ttu-id="5cbf1-103">Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="5cbf1-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="5cbf1-104">Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5cbf1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5cbf1-105">Atributo reconocido por el compilador que se usa para marcar un tipo o que se puede llamar como desusado.</span><span class="sxs-lookup"><span data-stu-id="5cbf1-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="5cbf1-106">Elementos con nombre</span><span class="sxs-lookup"><span data-stu-id="5cbf1-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="5cbf1-107">NewName: [cadena](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5cbf1-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5cbf1-108">Nombre completo del tipo o al que se puede llamar para usar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5cbf1-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="5cbf1-109">Se establece en la cadena vacía si un tipo o al que se puede llamar se ha dejado de usar sin sustitución.</span><span class="sxs-lookup"><span data-stu-id="5cbf1-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>