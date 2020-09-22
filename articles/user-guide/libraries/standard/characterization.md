---
title: Caracterización y estadísticas de Quantum
description: Obtenga información sobre cómo se usan las estadísticas de medida de las estimaciones de fase para calcular los valores de resultado en la programación de Quantum.
author: bradben
uid: microsoft.quantum.libraries.characterization
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8dddc15354c32808e7ad1310bce233ee3dc93fe8
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835645"
---
# <a name="quantum-characterization-and-statistics"></a>Caracterización y estadísticas de Quantum #

Es fundamental poder caracterizar los efectos de las operaciones para desarrollar algoritmos Quantum útiles.
Esto supone un reto porque cada medida de un sistema Quantum produce como máximo un bit de información.
Con el fin de aprender un eigenvalue, es decir, un estado Quantum, los resultados de muchas medidas se deben unir para que el usuario pueda recopilar los numerosos bits de información necesarios para representar estos conceptos.
Los Estados de Quantum son especialmente vexing porque el [teorema sin clonación](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) indica que no hay ninguna manera de aprender un estado de Quantum arbitrario desde una sola copia del estado, ya que esto le permitirá realizar copias del estado.
Esta ofuscación del estado de cuanto del usuario se refleja en el hecho de que Q# no expone ni incluso define lo que *es* un estado para los programas Quantum.
Por tanto, el enfoque de la caracterización de Quantum consiste en tratar las operaciones y los Estados como Black-Box. Este enfoque comparte mucho en común con la práctica experimental de caracterización, comprobación y validación de Quantum (QCVV).

La caracterización es distinta de muchas de las otras bibliotecas descritas anteriormente.
El objetivo aquí es menos aprender información clásica sobre el sistema, en lugar de realizar una transformación de unitarios en un vector de estado.
Por lo tanto, estas bibliotecas deben mezclar el procesamiento de la información clásica y Quantum.


## <a name="iterative-phase-estimation"></a>Estimación de fases iterativas ##

La visualización de la programación Quantum en términos de caracterización de Quantum sugiere una alternativa útil a la estimación de la fase Quantum.
Es decir, en lugar de preparar una $n registro $-qubit para que contenga una representación binaria de la fase como en la estimación de la fase Quantum, podemos ver la estimación de la fase como el proceso por el que un agente *clásico* aprende las propiedades de un sistema Quantum a través de las mediciones.
Continuaremos como en el caso de Quantum mediante la fase Kickback para convertir las aplicaciones de una operación de caja negra en rotaciones por un ángulo desconocido, pero medirá el qubit de ancilla que giramos en cada paso inmediatamente después de la rotación.
Esto tiene la ventaja de que solo se requiere una sola qubit adicional para realizar la fase Kickback que se describe en el caso de Quantum, ya que a continuación se aprende la fase de los resultados de la medición en cada paso de forma iterativa.  
Cada uno de los métodos que se propone a continuación usa una estrategia diferente para diseñar experimentos y métodos de procesamiento de datos diferentes para aprender la fase.  Cada una de ellas tiene una ventaja exclusiva que abarca desde la existencia de rigurosos límites de errores hasta la capacidad de incorporar información anterior, tolerar errores o ejecutarse en la memoria limitted los equipos clásico.

En la explicación de la estimación de la fase iterativa, se considerará una $U unitario $ como una operación de caja negra.
Como se describe en la sección sobre Oracle en las [estructuras de datos](xref:microsoft.quantum.libraries.data-structures), los modelos de Canon, Q# tales como las operaciones, por el <xref:microsoft.quantum.oracles.discreteoracle> tipo definido por el usuario, definidas por el tipo de tupla `((Int, Qubit[]) => Unit : Adjoint, Controlled)` .
Concretamente, si es `U : DiscreteOracle` , `U(m)` implementa $U ^ m $ para `m : Int` .

Con esta definición en su lugar, cada paso de la estimación de la fase iterativa continúa mediante la preparación de un qubit auxiliar en el estado $ \ket{+} $ junto con el estado inicial $ \ket{\phi} $ que asumimos es un [Eigenvector](xref:microsoft.quantum.concepts.matrix-advanced) de $U (m) $, es decir, $U (m) \ket{\phi} = e ^ {im\phi} \ les {\ Phi} $.  
`U(m)`Después, se usa una aplicación controlada de que prepara el estado $ \left (R \_ 1 (m \phi) \ket{+} \right) \ket{\phi} $.
Como en el caso de Quantum, el efecto de una aplicación controlada de Oracle `U(m)` es exactamente el mismo que el efecto de aplicar $R _ 1 _ 1 para la fase desconocida en $ \ket{+} $, de modo que podamos describir los efectos de $U $ en este modo más sencillo.
Opcionalmente, el algoritmo rota el qubit de control aplicando $R _ 1 (-m\theta) $ para obtener un estado $ \ket{\psi} = \left (R \_ 1 (m [\phi-\theta]) \ket{+} \right) \ket{\phi} $ $.
El qubit auxiliar que se usa como control para `U(m)` se mide en el $X $ Basis para obtener un único clásico `Result` .

En este momento, reconstruir la fase de los `Result` valores obtenidos a través de la estimación de la fase iterativa es un problema de inferencia estadística clásico.
La búsqueda del valor de $m $ que maximiza la información obtenida, dado un método de inferencia fijo, es simplemente un problema en las estadísticas.
Resaltamos esto describiendo brevemente la estimación de fases iterativas en un nivel teórico en el parámetro Bayesiano estimación de formalismo antes de continuar con la descripción de los algoritmos estadísticos que se proporcionan en Q# Canon para resolver este problema de inferencia clásica.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Estimación de fase iterativa sin Eigenstates ###

Si se proporciona un estado de entrada que no es un eigenstate, lo que significa que si $U (m) \ket{\phi \_ j} = e ^ {im\phi \_ j} $, el proceso de estimación de fase no guía de manera no determinista el estado de Quantum hacia un único eigenstate de energía.  En última instancia, eigenstate converge en es el eigenstate que es más probable que produzca el observado `Result` .

En concreto, un único paso de PE realiza la siguiente transformación no unitario en un estado \begin{align} \ sum_j \sqrt{\Pr (\phi \_ j)} \ket{\phi \_ j} \mapsto \sum \_ j\frac {\ sqrt {\ PR (\phi \_ j)} \sqrt{\Pr (\text{result} | \phi \_ j)} \Ket{\phi \_ j}} {\sqrt{\Pr (\phi \_ j) \sum \_ j \Pr (\text{result} | \phi \_ j)}}.
\end{align} como este proceso se repite en varios `Result` valores, eigenstates que no tienen los valores máximos de $ \ prod_k \pr (\text{result} \_ k | \phi \_ j) $ se suprimirán de forma exponencial.
Como resultado, el proceso de inferencia tiende a converger en los Estados con un solo eigenvalue si los experimentos se eligen correctamente.

El teorema de Bayes sugiere además que el estado resultante de la estimación de la fase se escribe con el formato \begin{align} \frac{\sqrt{\Pr (\phi \_ j)} \sqrt{\Pr (\text{result} | \phi \_ j)} \ket{\phi \_ j}} {\sqrt{\Pr (\phi \_ j) \Sum \_ j \Pr (\text{result} | \phi \_ j)}} = \ sum_j \sqrt{\Pr (\phi \_ j | \text{result})} \ket{\phi \_ j}.
\end{align} aquí $ \Pr (\phi \_ j | \text{result}) $ puede interpretarse como la probabilidad de que se asignara a cada hipótesis sobre el eigenstates dado:

1. conocimiento del estado de cuanto antes de la medición.
2. conocimiento del eigenstates de $U $ y,
3. conocimiento del vectores propios de la $U $.

Aprender estas tres cosas suele ser exponencialmente difícil en un equipo clásico.
La utilidad de estimación de la fase se produce, sin tener en cuenta, por el hecho de que puede realizar este tipo de tarea de aprendizaje de Quantum sin conocer ninguno de ellos.
La estimación de fase por este motivo aparece dentro de varios algoritmos Quantum que proporcionan velocidad exponencial.

### <a name="bayesian-phase-estimation"></a>Estimación de la fase bayesiana ###

> [!TIP]
> Para obtener más información sobre la estimación de la fase bayesiana en la práctica, consulte el ejemplo de [**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation) .

La idea de la estimación de la fase bayesiana es sencilla.
Se recopilan estadísticas de medidas del Protocolo de estimación de fase y, a continuación, se procesan los resultados mediante la inferencia bayesiana y se proporciona una estimación del parámetro.
Este procesamiento ofrece una estimación de los eigenvalue y la incertidumbre de esa estimación.
También permite realizar experimentos adaptables y utilizar información anterior.
El principal inconveniente de los métodos es que exige la informática.

Para entender cómo funciona este proceso de inferencia bayesiana, considere el caso del procesamiento de un único `Zero` resultado.
Tenga en cuenta que $X = \ket{+} \bra{+}-\ket {-} \bra {-} $, de modo que $ \ket{+} $ es el único eigenstate positivo de $X $ correspondiente a `Zero` .
La probabilidad de observar `Zero` una [ `PauliX` medida](xref:microsoft.quantum.concepts.pauli) en el primer qubit dado un estado de entrada $ \ket{\psi}\ket{\phi} $ es, por lo tanto, \begin{Equation} \Pr (\texttt{Zero} | \psi) = \left | \braket{+ | \psi} \right | ^ 2.
\end{Equation} en el caso de la estimación de la fase iterativa, tenemos $ \ket{\psi} = R_1 (m [\phi-\theta]) \ket{+} $, de modo que \begin{align} \Pr (\texttt{Zero} | \phi; m, \theta) & = \left | \braket{+ | R_1 (m [\phi-\theta]) | +} \right | ^ 2 \\ \\ & = \left | \frac12 \left (\bra {0} + \bra {1} \right) \left (\ket {0} + e ^ {i m [\phi-\theta]} \ket {1} \right) \right | ^ 2 \\ \\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}} {2} \right | ^ 2 \\ \\ & = \cos ^ 2 (m [\phi-\theta]/2) \tag{★} \label{EQ: fase-Estimado-probabilidad}.
\end{Align} es decir, la estimación de la fase iterativa consiste en conocer la frecuencia de oscilación de una función sinusoidal, dada la capacidad de voltear una moneda con un sesgo dado por ese sinusoidal.
Después de la terminología clásica tradicional, llamamos a $ \eqref{EQ: Phase-est-probabilidad} $ la *función de probabilidad* para la estimación de fases iterativas.

Tras observar un `Result` de la función de probabilidad de estimación de fase iterativa, podemos usar la regla de Bayes para prescribir lo que creemos que la fase debe seguir esa observación.
Concretamente, \begin{Equation} \Pr (\phi | d) = \frac{\Pr (d | \phi) \Pr (\phi)} {\int \Pr (d | \phi) \Pr (\phi) {\mathrm d} \phi} \Pr (\phi), \end{Equation} donde $d \en \\ {\texttt{Zero}, \texttt{One} \\ } $ es a y `Result` donde $ \Pr (\phi) $ describe nuestras creencias anteriores sobre $ \phi $.
Esto hace que la naturaleza iterativa de la estimación de fase iterativa sea explícita, ya que la distribución posterior $ \Pr (\phi | d) $ describe nuestras creencias inmediatamente antes de la observación de la siguiente `Result` .

En cualquier momento durante este procedimiento, podemos informar de la fase $ \hat{\phi} $ inferido por el controlador clásico como \begin{Equation} \hat{\phi} \mathrel{: =} \expect [\phi | \text{Data}] = \int \phi \Pr (\phi | \text{Data}) {\mathrm d} \phi, \end{Equation} donde $ \text{Data} $ representa todo el registro de todos `Result` los valores obtenidos.

La inferencia bayesiana exacta es inestable.
Para ver este Imagine, queremos obtener información sobre una variable de $-bit $n $x $.
La distribución anterior $ \Pr (x) $ admite más de $2 ^ n $ valores hipotéticos de $x $.
Esto significa que, si necesitamos una estimación muy precisa de $x $, la estimación de la fase bayesiana puede requerir memoria y tiempo de procesamiento prohibidos.
En el caso de algunas aplicaciones, como la simulación de Quantum, la precisión limitted requerida no impide que otros métodos, como el algoritmo de mé, no puedan usar la inferencia de Bayesiano exacta en el paso de estimación de fase.  Por esta razón, también proporcionamos implementaciones para los métodos bayesiana aproximados, como la [estimación de fases de recorrido aleatorio (RWPE)](xref:microsoft.quantum.research.characterization.randomwalkphaseestimation) y los enfoques no Bayesiana, como la [sólida estimación de fase](xref:microsoft.quantum.characterization.robustphaseestimation).

### <a name="robust-phase-estimation"></a>Estimación de fase sólida ###

En el peor de los casos, un valor máximo de *una* reconstrucción exgresivo de una fase de la estimación de la fase de los resultados de la medición es exponencialmente fuerte. Por lo tanto, la mayoría de los algoritmos de estimación de fase práctica sacrifican cierta calidad en la reconstrucción, a cambio de una cantidad de procesamiento posterior clásico que, en su lugar, se escala polinomiales con el número de medidas realizadas.

Un ejemplo de este tipo con un paso de procesamiento posterior más eficaz es el [algoritmo de estimación de fase sólida](https://arxiv.org/abs/1502.02677), con su firma y sus entradas mencionadas anteriormente. Se supone que los cuadros de color unitarios de entrada $U $ se empaquetan como `DiscreteOracle` tipo y, por lo tanto, solo consulta las potencias enteras de controled-$U $. Si el estado de entrada del `Qubit[]` registro es eigenstate $U \ket{\psi} = e ^ {i\phi} \ les {\ PSI} $, el algoritmo de estimación de fase sólida devuelve una estimación $ \hat{\phi}\in [-\pi, \pi) $ de $ \phi $ como `Double` .

La característica más importante de una estimación de fase sólida, que se comparte con la mayoría de las otras variantes útiles, es que la calidad de reconstrucción de $ \hat{\phi} $ está en cierto sentido Heisenberg-Limited. Esto significa que si la desviación de $ \hat{\phi} $ del valor true es $ \sigma $, $ \sigma $ se escala inversamente proporcionalmente al número total de consultas $Q $ realizado en controled-$U $, es decir, $ \sigma = \mathcal{O} (1/Q) $. Ahora, la definición de la desviación varía entre distintos algoritmos de estimación. En algunos casos, puede significar que, al menos $ \mathcal{O} (1) $ probability, el error de estimación $ | \hat{\phi}-\phi | \_ \circ\le \sigma $ en algunas medidas circulares $ \circ $. Para una estimación de fase sólida, la desviación es precisamente la varianza $ \sigma ^ 2 = \mathbb{E} \_ \hat{\phi} [(\mod \_ {2 \ PI} (\hat{\phi}-\phi + \pi)-\pi) ^ 2] $ si desencapsulamos las fases periódicas en un único intervalo finito $ (-\pi, \pi] $. Más concretamente, la desviación estándar en una estimación de fase sólida satisface las desigualdades $ $ \begin{align} 2,0 \pi/Q \le \sigma \le 2 \ pi/2 ^ {n} \le 10.7 \ PI/Q, \end{align} $ $ donde se alcanza el límite inferior en el límite de asymptotically grande $Q $ y se garantiza el límite superior incluso para tamaños de ejemplo pequeños.  Tenga en cuenta que $n $ seleccionado por la `bitsPrecision` entrada, que define implícitamente $Q $.

Otros detalles relevantes incluyen, por ejemplo, la sobrecarga de espacio pequeña de solo $1 $ ancilla qubit, o que el procedimiento no es adaptable, lo que significa que la secuencia requerida de experimentos de Quantum es independiente de los resultados de la medida intermedia. En este y en los próximos ejemplos en los que la elección del algoritmo de estimación de fase es importante, uno debería hacer referencia a la documentación como @"microsoft.quantum.characterization.robustphaseestimation" y a las publicaciones a las que se hace referencia para obtener más información y para su implementación.

> [!TIP]
> Hay muchos ejemplos en los que se usa una estimación de fase sólida. Para estimar la fase en la extracción de la energía de estado de la alimentación de varios sistemas físicos, consulte el ejemplo de [ **simulación de H2** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line), el [ejemplo **SimpleIsing** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/simple)y el ejemplo de [ **Modelo Hubbard** ](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).


### <a name="continuous-oracles"></a>Oracle continuos ###

También se puede generalizar a partir del modelo de Oracle que se ha usado anteriormente para permitir Oracle en tiempo continuo, modelado por el tipo Canon <xref:microsoft.quantum.oracles.continuousoracle> .
Tenga en cuenta que en lugar de un único operador unitario $U $, tenemos una familia de operadores unitarios $U (t) $ para $t \en \mathbb{R} $, que $U (t) U (s) $ = $U (t + s) $.
Se trata de una instrucción más débil que en el caso discreto, ya que podemos crear un <xref:microsoft.quantum.oracles.discreteoracle> mediante la restricción de $t = m \, \delta t $ para algún $ \delta t $ fijo.
Por [teorema](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i H t) $ para algún operador $H $, donde $ \exp $ es la matriz exponencial tal y como se describe en [matrices avanzadas](xref:microsoft.quantum.concepts.matrix-advanced).
Un eigenstate $ \ket{\phi} $ de $H $ de modo que $H \ket{\phi} = \phi \ket{\phi} $ es también un eigenstate de $U (t) $ para todos los $t $, \begin{Equation} U (t) \ket{\phi} = e ^ {i \phi t} \ket{\phi}.
\end{equation}

Se puede aplicar el mismo análisis exacto descrito para la estimación de la [fase bayesiana](#bayesian-phase-estimation) y la función de probabilidad es exactamente la misma para este modelo de Oracle más general: $ $ \Pr (\texttt{Zero} | \phi; t, \theta) = \cos ^ 2 \ Left (\frac{t [\phi-\theta]} {2} \right).
$ $ Además, si $U $ es una simulación de un generador dinámico, como es el caso de la [simulación de Hamiltonian](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation), se interpreta $ \phi $ como una energía.
Por lo tanto, el uso de la estimación de fase con consultas continuas nos permite aprender el [espectro energético simulado de moléculas](https://arxiv.org/abs/quant-ph/0604193), [materiales](https://arxiv.org/abs/1510.03859) o [teorías de campo](https://arxiv.org/abs/1111.3633v2) sin tener que poner en peligro nuestra elección de experimentos al requerir que $t $ sea un entero.

### <a name="random-walk-phase-estimation"></a>Estimación de fase de recorrido aleatorio ###

Q# proporciona una aproximación útil de la estimación de la fase bayesiana diseñada para el uso de dispositivos cercanos a Quantum que funcionan mediante el acondicionamiento de un recorrido aleatorio en el registro de datos Obtenido de la estimación de la fase iterativa.
Este método es tanto adaptable como completamente determinista, lo que permite un escalado casi óptimo de errores en la fase estimada $ \hat{\phi} $ con sobrecargas de memoria muy bajas.

El protocolo utiliza un método de inferencia Bayesiano aproximado que supone que la distribución anterior es Gaussiano.
Esta suposición gaussiano nos permite usar una fórmula analítica para el experimento que minimiza la desviación posterior.
Después, el algoritmo, en función del resultado de ese experimento, desplaza la estimación de $ \phi $ a la izquierda o a la derecha en una cantidad predeterminada y reduce la varianza en una cantidad determinada previamente.
Esta media y desviación proporcionan toda la información necesaria para especificar un gaussiano anterior a $ \phi $ para el siguiente experimento.
Los errores de medición inesperados, o el resultado verdadero en las colas del inicial anterior, pueden hacer que este método produzca un error.
Se recupera de un error realizando experimentos para probar si la media y la desviación estándar actuales son adecuadas para el sistema.
Si no es así, el algoritmo realiza un paso inverso del recorrido y el proceso continúa.
La capacidad de desplazarse hacia atrás también permite que el algoritmo Aprenda incluso si la desviación estándar anterior inicial es inapropriately pequeña.

## <a name="calling-phase-estimation-algorithms"></a>Algoritmos de estimación de fase de llamada ##

Cada operación de estimación de fase que se proporciona con el Q# Canon toma un conjunto diferente de entradas que parametrizan la calidad que demandamos de la estimación final $ \hat{\phi} $.
Sin embargo, estas diversas entradas comparten varias entradas en común, de modo que la aplicación parcial a través de los parámetros de calidad da como resultado una firma común.
Por ejemplo, la <xref:microsoft.quantum.characterization.robustphaseestimation> operación que se describe en la siguiente sección tiene la firma siguiente:

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

La `bitsPrecision` entrada es única en `RobustPhaseEstimation` , mientras que `oracle` y `eigenstate` están en común.
Por lo tanto, como se aprecia en **H2Sample**, una operación puede aceptar un algoritmo de estimación de fase iterativa con una entrada del formulario `(DiscreteOracle, Qubit[]) => Unit` para permitir que un usuario especifique algoritmos de estimación de fase arbitrarios:

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

Estos pocos algoritmos de estimación de fase están optimizados para las distintas propiedades y parámetros de entrada, que deben entenderse para que sea la mejor opción para la aplicación de destino. Por ejemplo, algunos algoritmos de estimación de fase son adaptables, lo que significa que los pasos futuros se controlan de forma controlada por los resultados de la medición de los pasos anteriores. Algunos requieren la capacidad de exponentiater su unitario de cuadro negro de Oracle por poderes reales arbitrarios, y otros solo requieren potencias enteras, pero solo pueden resolver un módulo de estimación de fase $2 \ PI $. Algunos requieren muchos qubits auxiliares y otros solo requieren uno.

Del mismo modo, el uso de la estimación de fases de recorrido aleatorios se realiza de forma muy similar a la de otros algoritmos que se proporcionan con Canon:

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
