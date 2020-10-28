---
uid: Microsoft.Quantum.Diagnostics.Test
title: Tipo definido por el usuario de prueba
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 8030f6378ac0cb393c7ed2b9e636a7561e8943a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727190"
---
# <a name="test-user-defined-type"></a>Tipo definido por el usuario de prueba

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


Atributo reconocido por el compilador que se usa para marcar una prueba unitaria.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="executiontarget--string"></a>ExecutionTarget: [cadena](xref:microsoft.quantum.lang-ref.string)

