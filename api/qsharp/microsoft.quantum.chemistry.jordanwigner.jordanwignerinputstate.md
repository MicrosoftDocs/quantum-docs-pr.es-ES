---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: Tipo definido por el usuario JordanWignerInputState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 171a2999ab8c73925d4624c565bfd41a4e73c99d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727761"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>Tipo definido por el usuario JordanWignerInputState

Espacio de nombres: [Microsoft. Quantum. química. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Configura [](https://nuget.org/packages/)


Formato de los datos pasados de C# a Q # para representar la preparación del estado inicial, el significado de los datos representados viene determinado por el algoritmo que lo recibe.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

