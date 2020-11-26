---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Tipo definido por el usuario HTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204137"
---
# <a name="hterm-user-defined-type"></a>Tipo definido por el usuario HTerm

Espacio de nombres: [Microsoft. Quantum. química](xref:Microsoft.Quantum.Chemistry)

Paquete: [Microsoft. Quantum. química](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Formato de los datos pasados de C# a Q # para representar un término de Hamiltonian.
El significado de los datos representados viene determinado por el algoritmo que lo recibe.

```qsharp

newtype HTerm = (Int[], Double[]);
```

