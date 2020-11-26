---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Tipo definido por el usuario RequiresCapability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 0d9e4eb294b3ce91058c204d5dba37ea29b4ac28
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231014"
---
# <a name="requirescapability-user-defined-type"></a>Tipo definido por el usuario RequiresCapability

Espacio de nombres: [Microsoft. Quantum. targeting](xref:Microsoft.Quantum.Targeting)

Paquete: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Atributo reconocido por el compilador que se usa para marcar una función que se puede llamar con las capacidades de tiempo de ejecución que requiere.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>Elementos con nombre

### <a name="level--string"></a>Nivel: [cadena](xref:microsoft.quantum.lang-ref.string)

Nombre del nivel de capacidad en tiempo de ejecución requerido por el que se puede llamar.
### <a name="reason--string"></a>Motivo: [cadena](xref:microsoft.quantum.lang-ref.string)

Una descripción de por qué la función invocable requiere esta funcionalidad en tiempo de ejecución.

## <a name="remarks"></a>Observaciones

Este atributo se agrega automáticamente para que el compilador pueda invocarlo, a menos que ya exista una instancia de este atributo en el que se pueda llamar. No debe usarse excepto en casos excepcionales en los que el compilador no deduce correctamente la funcionalidad necesaria.

A continuación se muestra la lista de nombres de nivel de capacidad, con el fin de aumentar las capacidades o reducir las restricciones:

## `"BasicQuantumFunctionality"`

No se puede comparar la igualdad de los resultados de la medida.

## `"BasicMeasurementFeedback"`

Los resultados de la medición solo se pueden comparar para comprobar la igualdad en expresiones condicionales if-Statement en operaciones. El bloque de una instrucción If que depende de un resultado no puede contener instrucciones SET para variables mutables declaradas fuera del bloque o instrucciones Return.

## `"FullComputation"`

No hay restricciones en tiempo de ejecución. Se puede ejecutar cualquier programa de preguntas y respuestas.