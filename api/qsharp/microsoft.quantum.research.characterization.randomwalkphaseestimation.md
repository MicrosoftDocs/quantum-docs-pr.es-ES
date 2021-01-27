---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Operación RandomWalkPhaseEstimation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845996"
---
# <a name="randomwalkphaseestimation-operation"></a>Operación RandomWalkPhaseEstimation

Espacio de nombres: [Microsoft. Quantum. Research. Caracterización](xref:Microsoft.Quantum.Research.Characterization)

Paquete: [Microsoft. Quantum. Research. Caracterización](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)


Realiza una estimación de la fase iterativa mediante un recorrido aleatorio para la inferencia bayesiana aproximada en los resultados de medidas clásicas de una determinada Oracle y eigenstate.

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Entrada

### <a name="initialmean--double"></a>initialMean: [Double](xref:microsoft.quantum.lang-ref.double)

Media de la distribución previa normal inicial a través de $ \phi $.


### <a name="initialstddev--double"></a>initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)

Desviación estándar de la distribución previa normal inicial a través de $ \phi $.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Número de medidas que se van a aceptar en la estimación posterior final.


### <a name="maxmeasurements--int"></a>maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Número total de medidas que se pueden realizar antes de que se considere que se ha producido un error en la operación.


### <a name="unwind--int"></a>desenredar: [int](xref:microsoft.quantum.lang-ref.int)

Número de resultados que se deben olvidar cuando se produce un error en las comprobaciones de coherencia.


### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Operación que representa una $U unitario $ de modo que $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $ with Unknown Phase $ \phi \en \mathbb{R} ^ + $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro en el que $U $ actúa.



## <a name="output--double"></a>Salida: [Double](xref:microsoft.quantum.lang-ref.double)

La estimación final $ \hat{\phi} \mathrel{: =} \expect [\phi] $, donde la expectativa se encuentra sobre el asiento en función de todos los datos aceptados.

## <a name="remarks"></a>Observaciones

### <a name="iterative-phase-estimation-and-eigenstates"></a>Estimación de fase iterativa y Eigenstates

En general, el registro de entrada `eigenstate` no necesita ser un eigenstate $ \ket{\phi} $ de $U $, pero puede ser una superposición sobre eigenstates. Supongamos que el estado de entrada lo proporciona \begin{align} \ket{\psi} & = \sum \_ {j} \alpha \_ j \ket{\phi \_ j}, \end{align} donde $ \{ \alpha \_ j \} $ son coeficientes complejos, de modo que $ \sum \_ j | \alpha \_ j | ^ 2 = $1 y Where $U \ket{\phi \_ j} = \phi \_ j\ket {\ Phi \_ j} $.

Después, realizar una estimación de la fase iterativa se convergirá en un único eigenstate, como se describe en la [Guía de desarrollo](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).

### <a name="experiment-design"></a>Diseño de experimentos

Los tiempos de medición $t $ y los ángulos de inversion $ \theta $ pasados a `oracle` se eligen según la heurística de la *partícula*, \Begin{align} \theta \sim \Pr (\phi), \quad t \approx \frac {1} {\variance{\phi}}.
\end{align} esta heurística es óptima para reducir la desviación posterior esperada en la estimación de la fase iterativa bajo la suposición de una normal anterior.

### <a name="optimality"></a>Idoneidad

Esta operación aproxima el estimador óptimo para la fase $ \phi $, tal como se ha evaluado mediante la pérdida cuadrática $L (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $.

Consulte [estimación de la fase bayesiana](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) para obtener más detalles sobre las estadísticas de la estimación de la fase iterativa.

## <a name="references"></a>Referencias

- Ferrie *et al.* 2011 [doi: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arXiv: 1110.3067](https://arxiv.org/abs/1110.3067).
- Wiebe *et al.* 2013 [doi: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv: 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe y Granade 2018 *(en preparación)*.