---
title: 'Bibliotecas de Q # Standard: estructuras de datos | Microsoft Docs'
description: 'Bibliotecas de Q # Standard: estructuras de datos'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e8b28561f1aba37cb5bf41c6176386d19bfacf06
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184515"
---
# <a name="data-structures-and-modeling"></a>Modelado y estructuras de datos #

## <a name="classical-data-structures"></a>Estructuras de datos clásicas ##

Junto con los tipos definidos por el usuario para representar los conceptos de Quantum, el Canon también proporciona operaciones, funciones y tipos para trabajar con datos de uso clásico en el control de sistemas Quantum.
Por ejemplo, la función <xref:microsoft.quantum.arrays.reversed> toma una matriz como entrada y devuelve la misma matriz en orden inverso.
A continuación, se puede usar en una matriz de tipo `Qubit[]` para evitar tener que aplicar las puertas $ \operatorname{SWAP} $ innecesarias al convertir entre representaciones de Quantum de enteros.
Del mismo modo, vimos en la sección anterior que los tipos de `(Int, Int -> T)` de formulario pueden ser útiles para representar colecciones de acceso aleatorio, por lo que la función <xref:microsoft.quantum.arrays.lookupfunction> proporciona una manera convienent de construir estos tipos a partir de tipos de matriz.

### <a name="pairs"></a>Pair ###

Canon admite la notación de estilo funcional para pares, que complementa el acceso a tuplas mediante la desconstrucción:

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>Matrices ###

La Canon proporciona varias funciones para manipular matrices.
Estas funciones son con parámetros de tipo y, por tanto, se pueden usar con matrices de cualquier tipo de Q #.
Por ejemplo, la función <xref:microsoft.quantum.arrays.reversed> devuelve una nueva matriz cuyos elementos están en orden inverso al de su entrada.
Se puede usar para cambiar el modo en que se representa un registro de Quantum cuando se llama a las operaciones:

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

Del mismo modo, la función <xref:microsoft.quantum.arrays.subarray> se puede usar para reordenar o tomar subconjuntos de los elementos de una matriz:

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

Cuando se combina con el control de flujo, las funciones de manipulación de matrices como <xref:microsoft.quantum.arrays.zip> pueden proporcionar una manera eficaz de expresar programas Quantum:

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Oracle ##

En la literatura de estimación de la [fase](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm) y de la [amplificación de amplitud](https://en.wikipedia.org/wiki/Amplitude_amplification) , el concepto de Oracle aparece con frecuencia.
Aquí el término Oracle hace referencia a una subrutina caja negra Quantum que actúa sobre un conjunto de qubits y devuelve la respuesta como una fase.
Esta subrutina a menudo se puede considerar como una entrada a un algoritmo Quantum que acepta Oracle, además de otros parámetros, y aplica una serie de operaciones Quantum y el tratamiento de una llamada a esta subrutina Quantum como si fuera una puerta fundamental.
Obviamente, para implementar el algoritmo más grande, se debe proporcionar una descomposición concreta de Oracle en las puertas fundamentales, pero no es necesaria una descomposición para comprender el algoritmo que llama a Oracle.
En Q #, esta abstracción se representa mediante el uso de que las operaciones son valores de primera clase, de modo que las operaciones se pueden pasar a las implementaciones de los algoritmos Quantum de manera negra.
Además, los tipos definidos por el usuario se usan para etiquetar las distintas representaciones de Oracle de una manera con seguridad de tipos, lo que dificulta la creación accidental de diferentes tipos de operaciones de caja negra.

Estas Oracle aparecen en varios contextos diferentes, incluidos ejemplos famosos como los algoritmos [de búsqueda y de simulación de Quantum de Grover](https://en.wikipedia.org/wiki/Grover%27s_algorithm) .
Aquí nos centramos en los Oracle necesarios solo para dos aplicaciones: amplificación de amplitud y estimación de fase.
En primer lugar, analizaremos la amplificación de amplitud Oracle antes de prousar la estimación de fase.

### <a name="amplitude-amplification-oracles"></a>Oracle de amplificación de amplitud ###

El algoritmo de amplificación de amplitud pretende realizar una rotación entre un estado inicial y un estado final aplicando una secuencia de reflexiones del estado.
Para que el algoritmo funcione, necesita una especificación de ambos Estados.
Estas especificaciones las proporcionan dos Oracle.
Estas Oracle funcionan dividiendo las entradas en dos espacios, un subespacio de "destino" y un subespacio "inicial".
Los Oracle identifican estos subespacios, de forma similar al modo en que los operadores de Pauli identifican dos espacios, aplicando una fase de $ \pm $1 a estos espacios.
La principal diferencia es que no es necesario que estos espacios estén en medio espacio en esta aplicación.
Tenga en cuenta también que estos dos subespacios no suelen ser mutuamente excluyentes: habrá vectores que sean miembros de ambos espacios.
Si no se cumple esto, la amplificación de amplitud no tendría ningún efecto, por lo que necesitamos que el subespacio inicial tenga una superposición distinta de cero con el subespacio de destino.

Indicaremos la primera Oracle que necesitamos para que se $P la amplificación de amplitud\_$0, que se define para que tenga la siguiente acción.  Para todos los Estados $ \ket{x} $ en el subespacio "inicial" $P\_0 \ket{x} =-\ket{x} $ y para todos los Estados $ \ket{y} $ que no están en este subespacio, tenemos $P\_0 \ket{y} = \ket{y} $.
La Oracle que marca el subespacio de destino, $P _ 1 _, toma exactamente la misma forma.
Para todos los Estados $ \ket{x} $ en el subespacio de destino (es decir, para todos los Estados en los que desea que se genere el algoritmo), $P _ 1 \ les {x} =-\ket{x} $.
Del mismo modo, para todos los Estados $ \ket{y} $ que no están en el subespacio de destino $P _ 1 \ les {y} = \ket{y} $.
A continuación, estas dos reflexiones se combinan para formar un operador que actúe en un único paso de amplificación de amplitud, $Q =-P_0 P_1 $, donde el signo menos global solo es importante tener en cuenta en las aplicaciones controladas.
La amplificación de amplitud procede entonces tomando un estado inicial, $ \ket{\psi} $ que se encuentra en el subespacio inicial y, a continuación, realiza $ \ket{\psi} \mapsto Q ^ m \ket{\psi} $.
La realización de este tipo de iteración garantiza que, si se inicia con un estado inicial que se superpone a $ \sin ^ 2 (\theta) $ con el espacio marcado, después de $m $ ITERATIONS esta superposición se convierte en $ \sin ^ 2 ([2m + 1] \theta) $.
Por lo tanto, normalmente queremos elegir $m $ para ser un parámetro gratuito, de modo que $ [2m + 1] \theta = \ pi/2 $; sin embargo, estas opciones rígidas no son tan importantes para algunas formas de amplificación de amplitud, como la amplificación de amplitud de punto fijo.
Este proceso nos permite preparar un estado en el subespacio marcado usando de forma cuadrática menos consultas a la función de marcado y la función de preparación de estado que sería posible en un dispositivo estrictamente clásico.
Este es el motivo por el que la amplificación de amplitud es un bloque de creación importante para muchas aplicaciones de la informática Quantum.

Con el fin de comprender cómo usar el algoritmo, es útil proporcionar un ejemplo que proporciona una construcción de Oracle.  Considere la posibilidad de realizar búsquedas en el algoritmo de Grover en esta configuración.
En la búsqueda de Grover, el objetivo es transformar el estado $ \ket{+} ^ {\otimes n} = H ^ {\otimes n} \ket{0}$ en uno de (potencialmente) muchos Estados marcados.
Para simplificar aún más, veamos el caso en el que el único estado marcado es $ \ket{0}$.
Después tenemos un diseño de dos Oracle: uno que solo marca el estado inicial $ \ket{+} ^ {\otimes n} $ con un signo menos y otro que marca el estado marcado $ \ket{0}$ con un signo menos.
La última puerta se puede implementar mediante la siguiente operación de procesamiento, mediante el uso de las operaciones de flujo de control en Canon:

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

Este es un caso especial de la operación de <xref:microsoft.quantum.canon.rall1>, que permite rotar por una fase arbitraria en lugar de por el caso de reflexión $ \phi = \pi $.
En este caso, `RAll1` es similar a la operación de pre\ket{11\cdots1}ción de <xref:microsoft.quantum.intrinsic.r1>, en que gira aproximadamente $ $ en lugar del estado de qubit único $ \ket{1}$.

El Oracle que marca el subespacio inicial se puede construir de forma similar.
En pseudocódigo:

1. Aplique $H $ Gates a cada qubit.
2. Aplique $X $ Gates a cada qubit.
3. Aplique un $n-$1 controlado $Z $-Gate al $n ^ {\text{TH}} $ qubit.
4. Aplique $X $ Gates a cada qubit.
5. Aplique $H $ Gates a cada qubit.

Esta vez, también se muestra el uso de <xref:microsoft.quantum.canon.applywith> junto con la operación de <xref:microsoft.quantum.canon.rall1> descrita anteriormente:

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

A continuación, podemos combinar estos dos Oracle juntos para rotar entre los dos Estados y transformar de forma determinista $ \ket{+} ^ {\otimes n} $ en $ \ket{0}$ mediante un número de capas de puertas de Hadamard que es proporcional a $ \sqrt{2 ^ n} $ (IE $m \propto \sqrt{2 ^ n} $) en comparación con las capas aproximadamente de $2 ^ n $ que se necesitarían para preparar de forma no determinista el estado $ \ket{0}$ al preparar y medir el estado inicial hasta que se observe el resultado $0 $.

### <a name="phase-estimation-oracles"></a>Estimación de fase de Oracle ###

En el caso de la estimación por fases, los Oracle son algo más naturales.
El objetivo de la estimación de la fase es diseñar una subrutina que sea capaz de realizar el muestreo desde el vectores propios de una matriz de una unitario.
Este método es indispensable en la simulación de Quantum porque, en el caso de muchos problemas físicos en química y ciencia de materias, estos vectores propios proporcionan el esfuerzos de estado de fondo de los sistemas Quantum, que nos proporciona información valiosa sobre los diagramas de fases de materiales y dinámica de reacción para moléculas.
Cada tipo de estimación de fase necesita una unitario de entrada.
Esta unitario se describe habitualmente mediante uno de dos tipos de Oracle.

> [!TIP]
> Los dos tipos de Oracle descritos a continuación se describen en los ejemplos.
> Para obtener más información acerca de las Oracle de consulta continua, consulte el ejemplo de [ **PhaseEstimation** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/PhaseEstimation).
> Para obtener más información sobre Oracle de consultas discretas, consulte el [ejemplo de **IsingPhaseEstimation** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingPhaseEstimation).

El primer tipo de Oracle, que llamamos una consulta discreta de Oracle y que se representa con el tipo definido por el usuario <xref:microsoft.quantum.oracles.discreteoracle>, simplemente implica una matriz de unitarios.
Si $U $ es la unitario cuyo vectores propios desea calcular, Oracle para $U $ es simplemente un producto para una subrutina que implementa $U $.
Por ejemplo, podría tomar $U $ para ser el $Q de Oracle $ definido anteriormente para la estimación de amplitud.
La vectores propios de esta matriz se puede usar para calcular la superposición entre los Estados inicial y de destino, $ \sin ^ 2 (\theta) $, lo que significa que, de lo contrario, se necesitarán menos muestras que una.
Esto gana la aplicación de la estimación de fase mediante el Grover Oracle $Q $ como entrada el moniker de la estimación de amplitude.
Otra aplicación común, ampliamente utilizada en la metrología de Quantum, implica la estimación de un ángulo de rotación pequeño.
En otras palabras, deseamos calcular $ \theta $ para una puerta de rotación desconocida con el formato $R _z (\theta) $.
En tales casos, la subrutina con la que interactuamos con el fin de aprender este valor fijo de $ \theta $ para la puerta es $ $ \begin{align} U & = R_z (\theta) \\\\ & = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\\\ 0 & e ^ {i \ Theta/2} \end{bmatrix}.
\end{align} $ $

El segundo tipo de Oracle que se usa en la estimación de fase es la consulta continua de Oracle, representada por el tipo de <xref:microsoft.quantum.oracles.continuousoracle>.
Una consulta continua de Oracle para la estimación de fase adopta el formato $U (t) $, donde $t $ es un número real conocido por clase.
Si se permite que $U $ sea una unidad fija, la consulta continua Oracle adopta la forma $U (t) = U ^ t $.
Esto nos permite consultar matrices como $ \sqrt{U} $, que no se pudieron implementar directamente en el modelo de consulta discreta.

Este tipo de Oracle es valioso cuando no está sondeando una unitario determinada, sino que desea conocer las propiedades del generador de la unitario.
Por ejemplo, en la simulación de quantums dinámicas, el objetivo es diseñar circuitos Quantum que se aproximen a $U (t) = e ^ {-i H t} $ para una matriz de Hermitian $H $ y el tiempo de evolución $t $.
El vectores propios de $U (t) $ está directamente relacionado con el vectores propios de $H $.
Para ver esto, considere la posibilidad de una Eigenvector de $H $: $H \ket{E} = E\ket {E} $, es fácil ver a partir de la definición de la serie potencia de la matriz exponencial que $U (t) \ket{E} = E ^ {i\phi} \ les {E} = E ^ {-iEt} \ket{E} $.
Por lo tanto, la estimación del eigenphase de $U (t) $ proporciona el eigenvalue $E $ suponiendo que Eigenvector $ \ket{E} $ sea una entrada en el algoritmo de estimación de fase.
Sin embargo, en este caso, se puede elegir el valor $t $ a discreción del usuario, ya que para cualquier valor suficientemente pequeño de $t $, eigenvalue $E $ se puede invertir de forma exclusiva mediante $E =-\ Phi/t $.
Dado que los métodos de simulación de Quantum proporcionan la capacidad de realizar una evolución fraccionaria, esto concede a los algoritmos de estimación de fase una libertad adicional al consultar la unitario, específicamente mientras que el modelo de consulta discreta solo permite unitaries del formulario $U ^ j $ para aplicarlo a un entero $j $ la consulta continua Oracle nos permite aproximar unitaries del formulario $U ^ t $ para cualquier valor real $t $.
Esto es importante para compensar todos los últimos onzas de rendimiento de los algoritmos de estimación de fase, ya que nos permite elegir precisamente el experimento que proporcionaría más información sobre $E $; mientras que los métodos basados en consultas discretas deben hacer lo que están en peligro eligiendo el mejor número entero de consultas en el algoritmo.

Como ejemplo concreto, tenga en cuenta el problema de la estimación del ángulo de rotación de una puerta, pero la frecuencia de procesamiento de un sistema Quantum giratorio.
La unitario que describe la dinámica de este tipo es $U (t) = R_z (2 \ Omega t) $ para el tiempo de evolución $t $ y la frecuencia desconocida $ \omega $.
En este contexto, se puede simular $U (t) $ para cualquier $t $ mediante un solo $R _z $ Gate y, como tal, no es necesario restringir solo las consultas discretas a la unitario.
Este modelo continuo también tiene la propiedad cuya frecuencia es mayor que $2 \ PI $ se puede obtener de los procesos de estimación de fase que usan consultas continuas, ya que la información de fase que, de otro modo, se enmascararía mediante las ramas de la función logarítmica. revelarse a partir de los resultados de los experimentos realizados en valores no acordes de $t $.
Por lo tanto, para problemas como estos modelos de consulta continua para la estimación de fase, Oracle no solo es adecuado, sino que también son preferibles al modelo de consulta discreto.
Por esta razón, Q # tiene funcionalidad para ambas formas de consultas y la deja al usuario para decidir si un algoritmo de estimación de fase se ajusta a sus necesidades y el tipo de Oracle que está disponible.

## <a name="dynamical-generator-modeling"></a>Modelado dinámico de generadores ##

Los generadores de la evolución temporal describen cómo evolucionan los Estados a lo largo del tiempo. Por ejemplo, la fórmula Dynamics de un estado Quantum $ \ket{\psi} $ se rige por la ecuación Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ con una matriz Hermitian $H $, conocida como Hamiltonian, como generador de disminuir. Dado un estado inicial $ \ket{\psi (0)} $ en el momento $t = $0, la solución formal a esta ecuación en el momento $t $ puede ser, en principio, escribir $ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}, \end{align} $ $ donde la matriz exponencial $U (t) = e ^ {-i H t} $ se conoce como operador de evolución de tiempo unitario. Aunque nos centramos en los generadores de este formulario en lo que se indica a continuación, se resalta que el concepto se aplica de forma más amplia, como la simulación de sistemas de Quantum abiertos, o a ecuaciones diferenciales más abstractas.

Un objetivo principal de la simulación dinámica es implementar el operador de evolución de tiempo en algún Estado de Quantum codificado en qubits de un equipo Quantum.  En muchos casos, el Hamiltonian se puede dividir en una suma de algunos $d $ más sencillos.

$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

en el caso de que la evolución de la hora por cada término solo sea fácil de implementar en un equipo Quantum. Por ejemplo, si $H _J $ es un operador Pauli $X _1X_2 $ que actúa sobre los elementos 1 y 2 de la `qubits`de registro qubit, la evolución de la hora de este en cualquier momento $t $ se puede implementar simplemente mediante una llamada a la operación `Exp([PauliX,PauliX], t, qubits[1..2])`, que tiene `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`de firma. Como se describe más adelante en la simulación de Hamiltonian, una solución consiste en aproximar la evolución del tiempo mediante $H $ con una secuencia de operaciones más sencillas.

$ $ \begin{align} U (t) & = \left (e ^ {-admitir\_0 t/r} e ^ {-admitir\_1 t/r} \cdots e ^ {-admitir\_{d-1} t/r} \right) ^ {r} + \mathcal{O} (d ^ 2 \max_j \\| H\_j\\| ^ 2 t ^ 2/r), \end{align} $ $

donde el entero $r > $0 controla el error de aproximación.

La biblioteca de modelado de generación dinámica proporciona un marco para codificar sistemáticamente generadores complicados en términos de generadores más sencillos. Una descripción de este tipo se puede pasar a, por ejemplo, a la biblioteca de simulación para implementar la evolución del tiempo mediante un algoritmo de simulación de elección, con muchos detalles que se deben tener en cuenta automáticamente.

> [!TIP]
> La biblioteca de generadores dinámicos que se describe a continuación se incluye en los ejemplos. Para ver un ejemplo basado en el modelo Ising, consulte el [ejemplo **IsingGenerators** ](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingGenerators).
> Para ver un ejemplo basado en hidrógeno molecular, consulte los ejemplos de [**H2SimulationCmdLine**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine) y [**H2SimulationGUI**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationGUI) .

### <a name="complete-description-of-a-generator"></a>Descripción completa de un generador ###

En el nivel superior, se incluye una descripción completa de un Hamiltonian en el `EvolutionGenerator` tipo definido por el usuario que tiene dos componentes:

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

El `GeneratorSystem` tipo definido por el usuario es una descripción clásica de Hamiltonian.

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

El primer elemento `Int` de la tupla almacena el número de términos $d $ en el Hamiltonian y el segundo elemento `(Int -> GeneratorIndex)` es una función que asigna un índice entero en $\{0, 1,..., d-1\}$ a un `GeneratorIndex` tipo definido por el usuario que identifica de forma única cada término primitivo en el Hamiltonian. Tenga en cuenta que al expresar la colección de términos de Hamiltonian como una función en lugar de como una matriz `GeneratorIndex[]`, esto permite realizar un cálculo sobre la marcha de la `GeneratorIndex`, lo que resulta especialmente útil al describir Hamiltonians con un gran número de términos.

De forma fundamental, no imponemos una Convención sobre qué términos primitivos identificados por el `GeneratorIndex` son fáciles de simular. Por ejemplo, los términos primitivos podrían ser operadores Pauli como se explicó anteriormente, pero también podrían ser Fermionic Annihilation y operadores de creación que se usan habitualmente en la simulación de química Quantum. Por sí solo, una `GeneratorIndex` no tiene sentido, ya que no describe cómo se puede implementar como un circuito Quantum la evolución del tiempo por el término al que señala.

Esto se resuelve especificando un `EvolutionSet` tipo definido por el usuario que asigna cualquier `GeneratorIndex`, que se extrae de un conjunto canónico, a un operador unitario, el `EvolutionUnitary`, expresado como un circuito de Quantum. El `EvolutionSet` define la Convención de cómo se estructura un `GeneratorIndex` y también define el conjunto de posibles `GeneratorIndex`.

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>Generadores de operadores Pauli ###

Un ejemplo concreto y útil de los generadores son Hamiltonians que son una suma de los operadores de Pauli, cada uno con un coeficiente diferente.
$ $ \begin{align} H & = \sum ^ {d-1} _ {j = 0} a_j H_j, \end{align} $ $, donde cada $ \hat H_j $ se extrae del grupo Pauli. Para estos sistemas, se proporciona la `PauliEvolutionSet()` de tipo `EvolutionSet` que define una Convención sobre cómo un elemento del grupo Pauli y un coeficiente puede identificarse mediante un `GeneratorIndex`, que tiene la siguiente firma.

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

En nuestra codificación, el primer parámetro `Int[]` especifica una cadena Pauli, donde $ \hat I\rightarrow $0, $ \hat X\rightarrow $1, $ \hat Y\rightarrow $2 y $ \hat Z\rightarrow $3. El segundo parámetro `Double[]` almacena el coeficiente de la cadena Pauli en Hamiltonian. Tenga en cuenta que solo se usa el primer elemento de esta matriz. El tercer parámetro `Int[]` indiza el qubits en el que actúa esta cadena Pauli y no debe tener elementos duplicados. Por lo tanto, Hamiltonian term $0,4 \hat X_0 \hat Y_8\hat I_2\hat Z_1 $ se puede representar como

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

El `PauliEvolutionSet()` es una función que asigna cualquier `GeneratorIndex` de este formulario a un `EvolutionUnitary` con la siguiente firma.

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

El primer parámetro representa una duración de tiempo, que se multiplicará por el coeficiente del `GeneratorIndex`de la evolución de la unitario. El segundo parámetro es el registro qubit en el que actúa la unitario. 

### <a name="time-dependent-generators"></a>Generadores dependientes del tiempo ###

En muchos casos, también estamos interesados en modelar generadores dependientes del tiempo, como pueden ocurrir en la ecuación Schrödinger $ $ \begin{align} i\frac {d \ket{\psi (t)}} {d t} & = \hat H (t) \ket{\psi (t)}, \end{align} $ $, donde el generador $ \hat H (t) $ es ahora dependiente del tiempo. La extensión de los generadores independientes del tiempo anteriores a este caso es sencilla. En lugar de tener un `GeneratorSystem` fijo que describa el Hamiltonian para todas las horas $t $, tenemos el `GeneratorSystemTimeDependent` tipo definido por el usuario.

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

El primer parámetro es un parámetro de programación continuo $s \en [0, 1] $, y las funciones de este tipo devuelven un `GeneratorSystem` para esa programación. Tenga en cuenta que el parámetro Schedule puede estar relacionado linealmente con el parámetro de hora física, por ejemplo $s = t/T $, durante un tiempo total de simulación $T $. Sin embargo, en general, esto no es necesario.

Del mismo modo, una descripción completa de este generador requiere un `EvolutionSet`, por lo que definimos un `EvolutionSchedule` tipo definido por el usuario.

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
