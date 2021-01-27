---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Función codificada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855495"
---
# <a name="encoded-function"></a>Función codificada

Espacio de nombres: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Codificar la tabla de verdad en la {1,-1} codificación

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>Entrada

### <a name="table--bool"></a>tabla: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabla de verdad como matriz de valores veracidad



## <a name="output--int"></a>Salida: [int](xref:microsoft.quantum.lang-ref.int)[]

Tabla de verdad como una matriz de {1,-1} enteros

## <a name="example"></a>Ejemplo

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```