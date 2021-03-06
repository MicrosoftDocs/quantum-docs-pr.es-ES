---
uid: Microsoft.Quantum.Canon.NoOp
title: Operación NoOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852390"
---
# <a name="noop-operation"></a>Operación NoOp

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Realiza la operación de identidad (no OP) en un argumento.

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Descripción

Esta operación toma un valor de cualquier tipo y no hace nada.
Esto puede ser útil siempre que se espera una entrada de un tipo de operación, pero no se debe realizar ninguna acción.
Por ejemplo, si un síndrome de corrección de errores determinado indica que no se ha producido ningún error, `NoOp<Qubit[]>` puede ser el procedimiento de recuperación correcto.
Del mismo modo, si una operación espera un procedimiento de preparación de estado como entrada, `NoOp<Qubit[]>` se puede usar para preparar el estado $ \ket{0 \cdots 0} $.

## <a name="input"></a>Entrada

### <a name="input--t"></a>entrada: ' t

Valor que se va a omitir.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parámetros de tipo

### <a name="t"></a>Traslada



## <a name="remarks"></a>Observaciones

En casi todos los casos, el parámetro de tipo de `NoOp` debe especificarse explícitamente. Por ejemplo, `NoOp<Qubit>` es idéntico a <xref:microsoft.quantum.intrinsic.i> .

## <a name="see-also"></a>Consulte también

- [Microsoft. Quantum. Intrinsic. I](xref:Microsoft.Quantum.Intrinsic.I)