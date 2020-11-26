---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operación DumpOperation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202063"
---
# <a name="dumpoperation-operation"></a>Operación DumpOperation

Espacio de nombres: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada una operación, muestra el diagnóstico de la operación que está disponible en el destino de ejecución actual.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Número de qubits en el que actúa la operación especificada.


### <a name="op--qubit--unit--is-adj"></a>OP: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = la [unidad](xref:microsoft.quantum.lang-ref.unit) > es ADJ

Operación que se va a diagnosticar.



## <a name="output--unit"></a>Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observaciones

La llamada a esta operación no tiene ningún efecto observable de en Q #. Los diagnósticos exactos que se muestran, si los hay, dependen del entorno del editor y del destino de ejecución actual.
Por ejemplo, cuando se usa en el simulador de Quantum de estado completo, se muestra una matriz de unitarios que se usa para representar `op` .

Tenga en cuenta que, cuando se ejecuta en simuladores que admiten una ambigüedad de fase global (por ejemplo, el simulador de estado completo), las representaciones devueltas pueden variar hasta una fase global.

Del mismo modo, el orden de las representaciones de las matrices de filas y columnas puede variar con las convenciones utilizadas por cada simulador que admite esta operación.