---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode función)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840493"
---
# <a name="graycode-function"></a>GrayCode función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea secuencias de código gris

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Entrada

### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Número de bits



## <a name="output--intint"></a>Salida: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Matriz de tuplas. El primer valor de la tupla es el valor del segundo valor de la secuencia GrayCode en la tupla es Position para cambiar en el valor actual para obtener el siguiente.

## <a name="example"></a>Ejemplo

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```