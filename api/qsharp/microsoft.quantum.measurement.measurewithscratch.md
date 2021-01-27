---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Operación MeasureWithScratch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854655"
---
# <a name="measurewithscratch-operation"></a>Operación MeasureWithScratch

Espacio de nombres: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Mide el operador de Pauli dado mediante un qubit de tachado explícito para realizar la medida.

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>Entrada

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Un operador Pauli de varios qubit especificado como una matriz de operadores Pauli de qubit único.


### <a name="target--qubit"></a>destino: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro de qubit que se va a medir.



## <a name="output--__invalidresult__"></a>Salida: __no <Result> válido__

Resultado de medir el operador Pauli determinado en el `target` registro.