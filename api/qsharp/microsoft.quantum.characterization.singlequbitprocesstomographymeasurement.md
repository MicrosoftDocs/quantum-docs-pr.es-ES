---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Operación SingleQubitProcessTomographyMeasurement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839650"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>Operación SingleQubitProcessTomographyMeasurement

Espacio de nombres: [Microsoft. Quantum. Caracterización](xref:Microsoft.Quantum.Characterization)

Paquete: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Realiza una medición de Tomography de proceso de un solo qubit en el Pauli, dado un canal concreto de interés.

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>Entrada

### <a name="preparation--pauli"></a>Preparación: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

El elemento Pauli base $P $ en el que se va a preparar una qubit.


### <a name="measurement--pauli"></a>medida: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

El elemento Pauli base $Q $ en el que se va a medir un qubit.


### <a name="channel--qubit--unit"></a>canal: [](xref:microsoft.quantum.lang-ref.qubit) => [unidad](xref:microsoft.quantum.lang-ref.unit) qubit 

Un único canal de qubit $ \Lambda $ cuyo comportamiento se está calculando con el proceso Tomography.



## <a name="output--__invalidresult__"></a>Salida: __no <Result> válido__

El resultado `Zero` con la probabilidad $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).
\end{align} $ $

## <a name="remarks"></a>Observaciones

La distribución de los resultados devueltos por esta operación es un caso especial de qubit de estado dos Tomography. Permita que $ \rho = J (\Lambda)/$2 sea el estado Choi – Jamiłkowski para $ \Lambda $. Después, la distribución anterior es idéntica a $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ Where $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 es la medida efectiva que corresponde a $P $ y $Q $.