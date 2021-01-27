---
uid: Microsoft.Quantum.Core.Deprecated
title: Tipo definido por el usuario en desuso
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832083"
---
# <a name="deprecated-user-defined-type"></a>Tipo definido por el usuario en desuso

Espacio de nombres: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Atributo reconocido por el compilador que se usa para marcar un tipo o que se puede llamar como desusado.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="newname--string"></a>NewName: [cadena](xref:microsoft.quantum.lang-ref.string)

Nombre completo del tipo o al que se puede llamar para usar en su lugar.
Se establece en la cadena vacía si un tipo o al que se puede llamar se ha dejado de usar sin sustitución.