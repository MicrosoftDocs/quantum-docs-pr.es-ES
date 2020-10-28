---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728697"
---
# <a name="graycode-function"></a>GrayCode función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Crea secuencias de código gris

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Entrada

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Número de bits



## <a name="output--intint"></a>Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Matriz de tuplas. El primer valor de la tupla es el valor del segundo valor de la secuencia GrayCode en la tupla es Position para cambiar en el valor actual para obtener el siguiente.