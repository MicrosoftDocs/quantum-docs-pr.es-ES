---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727203"
---
# <a name="formattedfailure-function"></a>FormattedFailure función)

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Configura [](https://nuget.org/packages/)


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