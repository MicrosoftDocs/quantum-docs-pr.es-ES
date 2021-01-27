---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828275"
---
# <a name="formattedfailure-function"></a>FormattedFailure función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Función interna que se usa para generar un error con mensajes de error significativos.

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--t"></a>real: ' t




### <a name="expected--t"></a>se esperaba: ' t




### <a name="message--string"></a>Message: [cadena](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

Esta función está pensada para ser emulada por los tiempos de ejecución de simulación, de modo que se permitan contradicciones con formato de reenvío.