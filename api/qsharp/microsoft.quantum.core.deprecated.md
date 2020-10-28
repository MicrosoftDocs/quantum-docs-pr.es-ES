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
# <a name="deprecated-user-defined-type"></a>Tipo definido por el usuario en desuso

Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Configura [](https://nuget.org/packages/)


Atributo reconocido por el compilador que se usa para marcar un tipo o que se puede llamar como desusado.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="newname--string"></a>NewName: [cadena](xref:microsoft.quantum.lang-ref.string)

Nombre completo del tipo o al que se puede llamar para usar en su lugar.
Se establece en la cadena vacía si un tipo o al que se puede llamar se ha dejado de usar sin sustitución.