---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits función)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728948"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits función)

Espacio de nombres: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Configura [](https://nuget.org/packages/)


Organizar el control, el destino y la aplicación auxiliar qubits según un índice

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Descripción

Devuelve una matriz de qubit con el destino en el índice 0 y el control i en el índice 2 ^ i.  La aplicación auxiliar qubits se inserta en todas las demás posiciones de la matriz.

## <a name="input"></a>Entrada

### <a name="controls--qubit"></a>controles: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>aplicación auxiliar: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Salida: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

