---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex función)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229297"
---
# <a name="identitygeneratorindex-function"></a>IdentityGeneratorIndex función)

Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devuelve un índice de generador coherente con el cero Hamiltonian, `H = 0` , que corresponde a la operación de evolución de identidad.

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrada

### <a name="idxterm--int"></a>idxTerm: [int](xref:microsoft.quantum.lang-ref.int)

Esta entrada se omite y se define para mantener la coherencia con el <xref:microsoft.quantum.simulation.generatorsystem> tipo definido por el usuario.



## <a name="output--generatorindex"></a>Salida: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Índice de generador que representa la evolución en el $H Hamiltonian = $0.