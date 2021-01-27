---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Contradicción (función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829359"
---
# <a name="contradiction-function"></a>Contradicción (función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Declara que una condición clásica es falsa.

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--bool"></a>real: [bool](xref:microsoft.quantum.lang-ref.bool)

Condición que se va a declarar.


### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)

Cadena de mensaje de error que se va a imprimir en caso de que la condición clásica sea true.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Ejemplo

El siguiente código de Q # imprimirá "Hello, World":

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Diagnostics. Fact](xref:Microsoft.Quantum.Diagnostics.Fact)