---
title: 'Bibliotecas de Q # Standard: aplicaciones | Microsoft Docs'
description: Bibliotecas estándar de Q#
author: QuantumWriter
uid: microsoft.quantum.libraries.applications
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3e629e095bd2ee492496066710ef6fd4e578a543
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868975"
---
# <a name="applications"></a>Aplicaciones #

## <a name="hamiltonian-simulation"></a>Simulación de Hamilton ##

La simulación de los sistemas Quantum es una de las aplicaciones más interesantes del cálculo de Quantum.
En un equipo clásico, la dificultad de simular la mecánica de Quantum, en general, se escala con la dimensión $N $ de su representación de vector de estado.
A medida que esta representación aumenta exponencialmente con el número de $n $ qubits $N = 2 ^ n $, un rasgo conocido que también se conoce como el [Curse de dimensionalidad](xref:microsoft.quantum.concepts.multiple-qubits), la simulación de Quantum en hardware clásico es inestable.

Sin embargo, la situación puede ser muy diferente en el hardware Quantum. La variación más común de la simulación de Quantum se denomina problema de simulación de Hamiltonian independiente del tiempo. Allí, se proporciona una descripción del sistema Hamiltonian $H $, que es una matriz Hermitian, y algunos estados iniciales de Quantum $ \ket{\psi (0)} $ que se codifican de alguna manera en $n $ qubits en un equipo Quantum. A medida que los Estados de Quantum en sistemas cerrados evolucionen con la ecuación Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ el objetivo es implementar el operador unitario Time-Evolution $U (t) = e ^ {-iHt} $ en un tiempo fijo $t $ , donde $ \ket{\psi (t)} = U (t) \ket{\psi (0)} $ resuelve la ecuación Schrödinger.
De forma análoga, el problema de simulación de Hamiltonian dependiente del tiempo resuelve la misma ecuación, pero con $H (t) $ ahora es una función de tiempo.

Hamiltonian Simulation es un componente importante de muchos otros problemas de simulación de Quantum y las soluciones para el problema de simulación de Hamiltonian son algoritmos que describen una secuencia de las puertas de Quantum primitivas para sintetizar una unidad aproximada de unidad de paso $ \tilde{U} $ con el error $\\| \tilde{U}-U (t)\\| \le \epsilon $ en la [norma espectral](xref:microsoft.quantum.concepts.matrix-advanced). La complejidad de estos algoritmos depende en gran parte del modo en que un equipo Quantum puede acceder a una descripción del Hamiltonian de interés. Por ejemplo, en el peor de los casos, si $H $ actuando en $n $ qubits se proporcionara como una lista de $2 ^ n \times 2 ^ n $ Numbers, uno para cada elemento de la matriz, la simple lectura de los datos ya requeriría tiempo exponencial. En el mejor de los casos, podría suponerse el acceso a una unitario de cuadro negro que $O \ket{t}\ket{\psi (0)} = \ket{t}U (t) \ket{\psi (0)} $ resuelve el problema de forma trivial. Ninguno de estos modelos de entrada es especialmente interesante (el primero, ya que no es mejor que los enfoques clásico, y el último como el negro oculta la complejidad de la puerta primitiva de su implementación, que podría ser exponencial en el número de qubits.

### <a name="descriptions-of-hamiltonians"></a>Descripciones de Hamiltonians ###

Por lo tanto, se requieren suposiciones adicionales del formato de la entrada. Se debe ajustar el equilibrio entre los modelos de entrada que son suficientemente descriptivos para abarcar Hamiltonians interesantes, como los de sistemas físicos realistas o problemas de cálculo interesantes, y los modelos de entrada suficientemente restrictivos. para que se pueda implementar de forma eficaz en un equipo Quantum. En la literatura se puede encontrar una variedad de modelos de entrada no triviales y que van desde Quantum hasta el clásico. 

Como ejemplos de modelos de entrada Quantum, [la simulación de Hamiltonian basada en muestras](http://www.nature.com/articles/s41534-017-0013-7) presupone el acceso de caja negra a las operaciones Quantum que producen copias de una matriz de densidad $ \rho $, que se toman para ser el Hamiltonian $H $. En el [modelo de acceso a](https://arxiv.org/abs/1202.5822) la unidad, suponemos que el Hamiltonian se descompone en una suma de unitaries $ $ \begin{align} H & = \sum ^ {d-1}\_{j = 0} a\_j \hat{U}\_j, \end{align} $ $, donde $a\_j > \hat{U} $ son coeficientes y $ unitaries\_j $ son. A continuación, se supone que una tiene acceso de caja negra a la unidad unitario de Oracle $V = \sum ^ {d-1}\_{j = 0} \ket{j}\bra{j}\otimes \hat{U}\_j $ que selecciona la $ \hat{U}\_j $, y Oracle $A \ket{0}= \sum ^ {d-1}\_{j = 0} \sqrt{a\_j/\ SUM ^ {d-1}\_{k = 0} \alpha\_j} \ket{j} $ que crean una codificación de estado de Quantum con estos coeficientes. En el caso de una [simulación Hamiltonian dispersa](https://arxiv.org/abs/quant-ph/0301023), se supone que Hamiltonian es una matriz dispersa con solo $d = \mathcal{O} (\Text{polylog} (N)) $ elemento distinto de cero en cada fila. Además, uno asume la existencia de circuitos Quantum eficientes que generan la ubicación de estos elementos distintos de cero, así como sus valores. La complejidad de los [algoritmos de simulación de Hamiltonian](xref:microsoft.quantum.more-information) se evalúa en cuanto al número de consultas a estas casillas negras, y la complejidad de la puerta primitiva depende en gran medida de la dificultad de implementar estos cuadros negros.

> [!NOTE]
> La notación Big-O se usa normalmente para describir el escalado de complejidad de los algoritmos. Dadas dos funciones reales $f, g $, la expresión $g (x) = \mathcal{O} (f (x)) $ significa que existe una constante positiva absoluta $x\_0, c > 0 $ de modo que $g (x) \le c f (x) $ para todos los $x \ge x\_$0. 

En la mayoría de las aplicaciones prácticas que se implementan en un equipo Quantum, estos cuadros negros deben ser implementables de forma eficaz, es decir, con $ \mathcal{O} (\text{polylog} (N)) $ primitivas de Quantum. De forma más segura, simulable Hamiltonians debe tener una descripción clásica suficientemente dispersa. En una de estas fórmulas, se da por supuesto que Hamiltonian se descompone en una suma de las partes de Hermitian $ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j.
\end{align} $ $ además, se supone que cada parte, un Hamiltonian $H\_j $, es fácil de simular. Esto significa que la $e unitario ^ {-admitir\_j t} $ en cualquier momento $t $ se puede implementar exactamente mediante $ \mathcal{O} (1) $ Primitive Quantum. Por ejemplo, esto es cierto en el caso especial en el que cada $H\_j $ son operadores de Pauli locales, lo que significa que son de tensores productos de los operadores $ \mathcal{O} (1) $ no Identity Pauli que actúan en qubits espacialmente cercanos. Este modelo se aplica especialmente a los sistemas físicos con interacción enlazada y local, ya que el número de términos es $d = \mathcal{O} (\text{polylog} (N)) $ y se puede escribir claramente, es decir, describirse de forma que es en el tiempo Polinómico.

> [!TIP]
> Hamiltonians que se descomponen en una suma de partes se pueden describir mediante la biblioteca de representación de generador dinámica. Para obtener más información, vea la sección representación dinámica del generador en [estructuras de datos](xref:microsoft.quantum.libraries.data-structures).

### <a name="simulation-algorithms"></a>Algoritmos de simulación ###

Un algoritmo de simulación de Quantum convierte una descripción determinada de un Hamiltonian en una secuencia de las puertas de Quantum primitivas que, en conjunto, se aproxima aproximadamente a la evolución de tiempo por dicho Hamiltonian.

En el caso especial en el que Hamiltonian se descomponga en una suma de partes de Hermitian, la descomposición Trotter-Suzuki es un algoritmo especialmente sencillo e intuitivo para simular Hamiltonians que se descomponen en una suma de componentes de Hermitian. Por ejemplo, un integrador de primera orden de esta familia se aproxima a $ $ \begin{align} U (t) & = \left (e ^ {-admitir\_0 t/r} e ^ {-admitir\_1 t/r} \cdots e ^ {-admitir\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j\\H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $ mediante un producto de $r d $ terms. 

> [!TIP]
> Las aplicaciones del algoritmo de simulación Trotter-Suzuki se describen en los ejemplos.
> Para el modelo Ising usando solo las operaciones intrínsecas proporcionadas por cada equipo de destino, consulte el [ejemplo **SimpleIsing** ](https://github.com/microsoft/Quantum/blob/master/samples/simulation/ising/simple).
> Para el modelo Ising que usa la estructura de control de la biblioteca Trotter-Suzuki, consulte el [ejemplo **IsingTrotter** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/trotter-evolution).
> Para el hidrógeno molecular mediante la estructura de control de la biblioteca Trotter-Suzuki, consulte el ejemplo de [ **simulación de H2** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line).

En muchos casos, nos gustaría implementar el algoritmo de simulación, pero no le interesan los detalles de su implementación. Por ejemplo, el integrador de segundo orden se aproxima a $ $ \begin{align} U (t) & = \left (e ^ {-admitir\_0 t/2R} e ^ {-admitir\_1 t/2R} \cdots e ^ {-admitir\_{d-1} t/2R} e ^ {-admitir\_{d-1} t/2R} \cdots e ^ {-admitir\_1 t/2R} e ^ {-admitir\_0 t/2R} \right) ^ {r} + \mathcal{O} (d ^ 3 \ max_j\\| H\_j\\| ^ 3 t ^ 3/r ^ 2), \end{align} $ $ mediante un producto de los términos $2rd $. Los pedidos más grandes implicarán aún más términos y las variantes optimizadas pueden requerir pedidos muy no triviales en el exponencial. Otros algoritmos avanzados también pueden implicar el uso de ancilla qubits en pasos intermedios. Por lo tanto, empaquetamos algoritmos de simulación en la Canon como el tipo definido por el usuario.

```qsharp
newtype SimulationAlgorithm = ((Double, EvolutionGenerator, Qubit[]) => Unit is Adj + Ctl);
```

El primer parámetro `Double` es la hora de la simulación, el segundo parámetro `EvolutionGenerator`, que se describe en la sección representación dinámica del generador de [estructuras de datos](xref:microsoft.quantum.libraries.data-structures), es una descripción clásica de un Hamiltonian independiente del tiempo que se empaqueta con instrucciones sobre cómo un circuito Quantum puede simular cada término de Hamiltonian. Los tipos de este formulario se aproximan a la operación unitario $e ^ {-iHt} $ en el tercer parámetro `Qubit[]`, que es el registro que almacena el estado de cuanto del sistema simulado. De forma similar al caso dependiente del tiempo, se define un tipo definido por el usuario con un tipo de `EvolutionSchedule` en su lugar, que es una descripción clásica de un Hamiltonian dependiente del tiempo.

```qsharp
newtype TimeDependentSimulationAlgorithm = ((Double, EvolutionSchedule, Qubit[]) => Unit : Adjoint, Controlled);
```

Por ejemplo, se puede llamar a la descomposición Trotter-Suzuki mediante las siguientes funciones de Canon, con parámetros `trotterStepSize` modificar la duración de la simulación en cada exponencial y `trotterOrder` para el orden del integrador deseado.

```qsharp
function TrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: SimulationAlgorithm {
    ...
}

function TimeDependentTrotterSimulationAlgorithm(
    trotterStepSize : Double, 
    trotterOrder : Int) 
: TimeDependentSimulationAlgorithm {
    ...
}
```

> [!TIP]
> Las aplicaciones de la biblioteca de simulación se describen en los ejemplos. Para calcular la fase en el modelo Ising con `SimulationAlgorithm`, consulte el [ejemplo **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).
> Para la preparación del estado de adiabatic en el modelo Ising mediante `TimeDependentSimulationAlgorithm`, consulte el [ejemplo **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).


### <a name="adiabatic-state-preparation--phase-estimation"></a>Preparación del estado de la Adiabatic & estimación de fase ###

Una aplicación común de la simulación de Hamiltonian es la preparación del estado de Adiabatic. En este caso, se proporciona uno con dos $H de Hamiltonians\_{\text{Start}} $ y $H\_{\text{end}} $ y un valor de Quantum $ \ket{\psi (0)} $ que es un estado de la base de inicio Hamiltonian $H\_{\text{Start}} $. Normalmente, se elige $H\_{\text{Start}} $, de modo que $ \ket{\psi (0)} $ sea fácil de preparar desde un estado de base de cálculo $ \ket{0\cdots 0} $. Al interpolar entre estos Hamiltonians en el problema de simulación dependiente del tiempo suficientemente lentamente, es posible terminar, con alta probabilidad, en el estado de la base de Hamiltonian $H final\_{\text{end}} $. Aunque la preparación de las buenas aproximaciones a los Estados de Hamiltonian puede continuar de esta manera llamando a en los algoritmos de simulación de Hamiltonian dependientes del tiempo como una subrutina, otros enfoques conceptualmente diferentes, como el cuanto de variación eigensolver son posibles.

Otra aplicación omnipresente en la química Quantum es estimar la energía de estado de la base de Hamiltonians que representa los pasos intermedios de la reacción química. Por ejemplo, un esquema de este tipo podría basarse en la preparación del estado de Adiabatic para crear el estado de la base y, a continuación, incorporar la simulación de Hamiltonian independiente del tiempo como subrutina en la caracterización de la fase de estimación para extraer esta energía con algún error finito y probabilidad de éxito. 

La abstracción de algoritmos de simulación como los tipos definidos por el usuario `SimulationAlgorithm` y `TimeDependentSimulationAlgorithm` permiten incorporar su funcionalidad a los algoritmos Quantum más sofisticados. Esto nos motiva a hacer lo mismo para estas subrutinas de uso frecuente.

Por lo tanto, definimos la función adecuada

```qsharp
function InterpolatedEvolution(
        interpolationTime : Double, 
        evolutionGeneratorStart : EvolutionGenerator,
        evolutionGeneratorEnd : EvolutionGenerator,
        timeDependentSimulationAlgorithm : TimeDependentSimulationAlgorithm)
: (Qubit[] => Unit is Adj + Ctl) {
        ...
}
 
```

Esto devuelve una operación de unitario que implementa todos los pasos de preparación del estado de Adiabatic. El primer parámetro `interpolatedTime` define el tiempo durante el que se interpolará linealmente entre el Hamiltonian de inicio descrito por el segundo parámetro `evolutionGeneratorStart` y el Hamiltonian final descrito por el tercer parámetro `evolutionGeneratorEnd`. El cuarto parámetro `timeDependentSimulationAlgorithm` es donde uno hace la elección del algoritmo de simulación. Tenga en cuenta que si `interpolatedTime` es lo suficientemente largo, un estado de la base inicial sigue siendo un estado de conexión de Hamiltonian en la totalidad de la duración de la simulación dependiente del tiempo y, por tanto, finaliza en el estado de conexión de la Hamiltonian final.

También se define una operación útil que realiza automáticamente todos los pasos de un experimento de química de Quantum típico. Por ejemplo, tenemos lo siguiente, que devuelve una estimación de energía del estado producido por la preparación del estado de Adiabatic:

```qsharp
operation EstimateAdiabaticStateEnergy(
    nQubits : Int,
    statePrepUnitary : (Qubit[] => Unit),
    adiabaticUnitary : (Qubit[] => Unit),
    qpeUnitary: (Qubit[] => Unit is Adj + Ctl),
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double {
...
}
```

`nQubits` es el número de qubits que se usan para codificar el estado de cuanto inicial. `statePrepUnitary` prepara el estado de inicio de la base de cálculo $ \ket{0\cdots 0} $. `adiabaticUnitary` es la operación unitario que implementa la preparación del estado de Adiabatic, como la generada por la función `InterpolatedEvolution`. `qpeUnitary` es la operación unitario que se utiliza para realizar una estimación de la fase en el estado de cuanto resultante. `phaseEstAlgorithm` es nuestra opción de algoritmo de estimación de fase.

> [!TIP]
> Las aplicaciones de preparación del estado de Adiabatic se describen en los ejemplos. Para el modelo Ising mediante una implementación manual de la preparación del estado de adiabatic en comparación con la función `AdiabaticEvolution`, consulte el [ejemplo **AdiabaticIsing** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/adiabatic).
> Para la estimación de la fase y la preparación del estado de adiabatic en el modelo Ising, consulte el [ejemplo **IsingPhaseEstimation** ](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation).

> [!TIP]
> La [simulación de hidrógeno molecular](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line) es un ejemplo interesante y breve. El modelo y los resultados experimentales que se muestran en [O'Malley et. al.](https://arxiv.org/abs/1512.06860) solo requiere matrices Pauli y tiene el formato $ \hat H = g\_{0}I\_0I\_1 + g\_1 {Z\_0} + g\_2 {Z\_1} + g\_3 {Z\_0} {Z\_1} + g\_4 {Y\_0} {Y\_1} + g\_5 {X\_0} {X\_1} $. Se trata de un Hamiltonian efectivo que solo requiere 2 qubits, donde las constantes $g $ se calculan a partir de la distancia $R $ entre los dos átomos de hidrógeno. Con las funciones de Canon, Paulis se convierte en unitaries y, a continuación, evolucionó durante breves períodos de tiempo mediante la descomposición Trotter-Suzuki. Se puede crear una buena aproximación a la $H _2 $ de la alimentación sin usar la preparación del estado de Adiabatic y, por tanto, la energía del estado de la base se puede encontrar directamente mediante la estimación de fase de la Canon.

## <a name="shors-algorithm"></a>Algoritmo de Shor ##
El algoritmo de mé sigue siendo uno de los progresos más importantes de la informática Quantum porque mostró que los equipos Quantum podrían usarse para resolver problemas importantes, que actualmente se pueden deducir.
El algoritmo de mé proporciona una manera rápida de factorizar números grandes mediante un equipo Quantum, un problema llamado *factorización*.
La seguridad de muchos cryptosystems de día presentes se basa en la suposición de que no existe ningún algoritmo rápido para la factorización.
Por lo tanto, el algoritmo de mé ha tenido un impacto profundo en cómo pensamos en la seguridad en un mundo posterior al Quantum.

El algoritmo de mé puede considerarse un algoritmo híbrido.
El equipo Quantum se usa para llevar a cabo una tarea computacionalmente difícil conocida como búsqueda de períodos.
Los resultados del período de búsqueda se procesan entonces de forma que se calculan los factores.
Estos dos pasos se revisan a continuación.

### <a name="period-finding"></a>Búsqueda de períodos ###

Después de ver cómo funciona la transformación de Fourier y la fase de estimación de las fases (consulte [algoritmos Quantum](xref:microsoft.quantum.libraries.standard.algorithms)), podemos usar estas herramientas para resolver un problema de cálculo de clase difícilmente llamado *período de búsqueda*.  En la siguiente sección, veremos cómo aplicar el período de búsqueda a la factorización.

Dados dos enteros $a $ y $N $, donde $a < N $, el objetivo de la búsqueda del período, también denominado búsqueda de pedidos, es encontrar el _orden_ $r $ de $a $ módulo $N $, donde $r $ se define como el entero menos positivo, de modo que $a ^ r \equiv 1 \text{mod} N $.  

Para encontrar el pedido mediante un equipo Quantum, podemos usar el algoritmo de estimación de fase que se aplica al siguiente Operador unitario $U _a $: $ $ U_a \ket{x} \equiv \ket{(AX) \text{mod} N}. $ $ vectores propios de $U _a $ son para el entero $s $ y $0 \ Leq s \leq r-$1, $ $ \ket{x_s} \equiv 1/\sqrt{r} \sum\_{k = 0} ^ {r-1} e ^ {\frac{-2\pi i SK} {r}} \ket{a ^ k\text {mod} N}, $ $ son _eigenstates_ de $U _a $.
La vectores propios de $U _a $ son $ $ U\_un \ket{x\_s} = e ^ {2 \ Pi i s/r} \ket{x\_s}. $$

Por lo tanto, la estimación de fase genera el vectores propios $e ^ {2 \ Pi i s/r} $ desde el que $r $ se puede aprender eficazmente mediante [fracciones continuas](https://en.wikipedia.org/wiki/Continued_fraction) de $s/r $.

El diagrama del circuito para buscar el período de Quantum es:

![](./../../media/QPE.svg)

Aquí $2N $ qubits se inicializan en $ \ket{0}$ y $n $ qubits se inicializan en $ \ket{1}$.
Es posible que el lector se pregunte por qué el registro de Quantum para contener el eigenstates se inicializa en $ \ket{1}$.
Como uno no conoce el orden $r $ de antemano, en realidad no se pueden preparar $ \ket{x_s} $ States directamente.
Afortunadamente, resulta que $1/\ sqrt {r} \sum\_{s = 0} ^ {r-1} \ket{x\_s} = \ket{1}$.
En realidad, no es necesario preparar $ \ket{x} $.
Solo se puede preparar un registro de Quantum de $n $ qubits en el estado $ \ket{1}$. 

El circuito contiene el QFT y varias puertas controladas.
La puerta QFT se ha descrito [anteriormente](xref:microsoft.quantum.libraries.standard.algorithms).
El $U controlado _a $ Gate asigna $ \ket{x} $ a $ \ket{(AX) \text{mod} N} $ si el control qubit es $ \ket{1}$ y asigna $ \ket{x} $ a $ \ket{x} $ en caso contrario.

Para lograr $ (a ^ NX) \text{mod} N $, podemos simplemente aplicar el $U controlado _ {a ^ n} $, donde calculamos $a ^ n \text{mod} N $ classly para conectarse al circuito Quantum.  
Los circuitos para lograr tal aritmética modular se han descrito en la [documentación aritmética de Quantum](./algorithms.md#arithmetic), en concreto, se requiere un circuito de exponenciación modular para implementar las operaciones de\_de $U controlado {a ^ i} $.

Aunque el circuito anterior corresponde a la estimación de la [fase de Quantum](xref:microsoft.quantum.characterization.quantumphaseestimation) y habilita explícitamente la búsqueda de pedidos, podemos reducir el número de qubits necesarias. Podemos seguir el método de Beauregard para buscar el orden, como se describe [en la página 8 de arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8), o usar una de las rutinas de estimación de fase disponibles en Microsoft. Quantum. Caracterización. Por ejemplo, la [estimación de fase sólida](xref:microsoft.quantum.characterization.robustphaseestimation) también usa un qubit adicional.
 
### <a name="factoring"></a>Factorización ###
El objetivo de la factorización es determinar los dos factores primos de entero $N $, donde $N $ es una $n número $-bit.  
La factorización consta de los pasos que se describen a continuación. Los pasos se dividen en tres partes: una rutina de preprocesamiento clásico (1-4); una rutina de procesamiento de quantums para buscar el orden de $a \text{mod} N $ (5); y una rutina de procesamiento de postprocesamiento clásico para derivar los factores primos del pedido (6-9).

La rutina de preprocesamiento clásico consta de los siguientes pasos:
1. Si $N $ es par, devuelve el factor primo $2 $.
2. Si $N = p ^ q $ para $p \geq1 $, $q \geq2 $, devuelve el factor primo $p $.  Este paso se realiza de forma de clase.
3. Elija un número aleatorio $a $ tal que $1 < un < N-$1.
4. Si $ \text{GCD} (a, N) > 1 $, devuelve el factor primo $ \text{GCD} (a, N) $. Este paso se calcula mediante el algoritmo de Euclides.
Si no se ha devuelto ningún factor primo, se pasa a la rutina Quantum:
5. Llame al algoritmo de búsqueda de período de Quantum para calcular el orden $r $ de $a \text{mod} N $. Use $r $ en la rutina de procesamiento de postprocesamiento clásico para determinar los factores primos:
6. Si $r $ es impar, vuelva al paso de preprocesamiento (3).
7. Si $r $ es par y $a ^ {r/2} =-1 \ Text {mod} N $, vuelva al paso de preprocesamiento (3).
8. Si $ \text{GCD} (a ^ {r/2} + 1, N) $ es un factor no trivial de $N $, devuelve $ \text{GCD} (a ^ {r/2} + 1, N) $.
9. Si $ \text{GCD} (a ^ {r/2}-1, N) $ es un factor no trivial de $N $, se devuelve $ \text{GCD} (a ^ {r/2}-1, N) $.


El algoritmo de factorización es probabilística: se puede mostrar que con probabilidad al menos una mitad que $r $ será par y $a ^ {r/2} \neq-1 \text{mod} N $, lo que genera un factor primo.  (Consulte el [documento original de mé](https://doi.org/10.1109/SFCS.1994.365700) para obtener más información o uno de los textos *básicos de cálculo de quantums* en [para obtener más información](xref:microsoft.quantum.more-information)).
Si no se devuelve un factor primo, simplemente repetiremos el algoritmo del paso (1).  Después de $n $ intentos, la probabilidad de que se haya producido un error en cada intento es como máximo $2 ^ {-n} $.
Por lo tanto, después de repetir el algoritmo, se garantiza prácticamente un número pequeño de veces.
