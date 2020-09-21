---
title: Algoritmos Quantum en Q#
description: Obtenga información acerca de los algoritmos de cálculo de Quantum fundamentales, como amplificación de amplitud, transformación de Fourier, agregadores de Draper y Beauregard y estimación de fases.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7ce13c5df3795656156cccf28640c0a4b0dcba2e
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835679"
---
# <a name="quantum-algorithms"></a>Algoritmos Quantum #

## <a name="amplitude-amplification"></a>Amplificación de amplitud ##

La *amplificación de amplitud* es una de las herramientas fundamentales de la informática Quantum. Es la idea fundamental que subyace en la búsqueda de Grover, la estimación de amplitudes y muchos algoritmos Quantum de aprendizaje automático.  Hay muchas variantes y en Q# se proporciona una versión general basada en la amplificación de amplitud desconocen con reflexiones parciales para permitir el área más amplia de la aplicación.

La idea central detrás de la amplificación de amplitud es ampliar la probabilidad de que se produzca un resultado deseado mediante la realización de una secuencia de reflejos.  Estas reflexiones giran el estado inicial más cerca de un estado de destino deseado, a menudo denominado estado marcado.  En concreto, si la probabilidad de medir el estado inicial en un estado marcado es $ \sin ^ 2 (\theta) $ después de aplicar la amplificación de amplitud $m $ veces, la probabilidad de éxito se convierte en $ \sin ^ 2 ((2m + 1) \theta) $.  Esto significa que si $ \theta = \ PI/[2 (2n + 1)] $ para algún valor de $n $, la amplificación de amplitud es capaz de aumentar la probabilidad de éxito hasta $100 \\ % $ después de $n $ iteraciones de amplificación de amplitud.  Dado que $ \theta = \sin ^ {-1} (\sqrt{\Pr (Success)}) $ esto significa que el número de iteraciones necesarias para obtener un correcto de forma determinista es cuadráticamente inferior al número esperado necesario para encontrar un estado marcado de manera no determinista mediante un muestreo aleatorio.

Cada iteración de amplificación de amplitud requiere que se especifiquen dos operadores de reflexión. En concreto, si $Q $ es la iteración de amplificación de amplitud y $P _0 $ es un operador de proyector en el subespacio inicial y $P _ _ 1 es el proyector en el subespacio marcado y $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Recuerde que un proyector es un operador de Hermitian que tiene vectores propios $ + $1 y $0 $ y como resultado $ (\boldone-2P_0) $ es unitario porque tiene vectores propios que son raíces de Unity (en este caso $ \pm $1). Como ejemplo, considere el caso de la búsqueda de Grover con el estado inicial $H ^ {\otimes n} \ket {0} $ y el estado marcado $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket {0} \bra {0} H ^ {\otimes n} $ y $P _ 1 = \ket{m}\bra{m} $.  En la mayoría de las aplicaciones de amplificación de amplitud $P _0 $ será un proyector en un estado inicial, lo que significa que $P _0 = \boldone-2 \ les {\ PSI} \ Bra {\ PSI} $ para algún vector $ \ket{\psi} $; sin embargo, para la amplitud desconocen amplication $P _0 $ se proyectará normalmente en muchos Estados Quantum (es decir, la multiplicidad de $ + $1 eigenvalue de $P _0 $ es mayor que $1 $).

La lógica que subyace a la amplificación de amplitud sigue directamente desde la propios-descomposición de $Q $.  En concreto, el vectores propios de $Q $ que tiene el estado inicial es una compatibilidad distinta de cero que se puede mostrar como una combinación lineal de $ + $1 vectores propios de $P _0 $ y $P _ 1 $.  En concreto, el estado inicial de amplificación de amplitud (suponiendo que es un Eigenvector de $ + $1 de $P _0 $) se puede escribir como $ $ \ket{\psi} = \frac{-i}{\sqrt {2} } \left (e ^ {i\theta} \ les {\ psi_ +} + e ^ {-i\theta} \ les {\ psi_-} \right). $ $ Where $ \ket{\ psi_ \pm} $ son vectores propios de $Q $ con vectores propios $e ^ {\pm 2i \ Theta} $ y solo tienen soporte técnico en el vectores propios $ + $1 de $P _0 $ y $P _ 1 $.  El hecho de que los vectores propios se $e ^ {\pm i \theta} $ implica que el operador $Q $ realiza una rotación en un subespacio bidimensional especificado por los dos proyectores y el estado inicial en el que el ángulo de rotación es $2 \ Theta $.  Por este motivo, después de $m $ ITERATIONS de $Q $, la probabilidad de éxito es $ \sin ^ 2 ([2m + 1] \theta) $.

Otra propiedad útil que sale de esto es que eigenvalue $ \theta $ está directamente relacionado con la probabilidad de que el estado inicial se marcara (en el caso de que $P _0 $ sea un proyector solo en el estado inicial).  Dado que el eigenphases de $Q $ son $2 \ Theta = 2 \ sin ^ {-1} (\sqrt{\Pr (Success)}) $, después, si aplicamos la estimación de fase a $Q $, podremos conocer la probabilidad de éxito de un procedimiento de Quantum unitario.  Esto resulta útil porque requiere menos aplicaciones del procedimiento Quantum de forma cuadrática para conocer la probabilidad de éxito que, de lo contrario, sería necesaria.

Q# introduce amplificación de amplitud como una especialización de amplificación de amplitud desconocen.  La amplificación de amplitud desconocen gana este moniker porque el proyector en el eigenspace inicial no debe ser un proyector en el estado inicial.  En este sentido, el protocolo se desconocen al estado inicial.  La aplicación clave de la amplificación de amplitud de desconocen es en determinadas *combinaciones lineales de métodos de simulación de Hamiltonian unitarios* , donde el estado inicial es desconocido, pero se pone inactiva con un registro ancilla en el protocolo de simulación.  Si este registro ancilla se mediera como un valor fijo, por ejemplo, $0 $, estos métodos de simulación aplican la transformación unitario deseada al Qubits restante (denominado registro del sistema).  Sin embargo, el resto de los resultados de medición conducen a errores.  La amplificación de amplitud desconocen permite aumentar la probabilidad de éxito de esta medida hasta $100 \\ % $ mediante el razonamiento anterior.  Además, la amplificación de amplitud normal se corresponde con el caso en el que el registro del sistema está vacío.  Este es el motivo por el Q# que usa la amplificación de amplitud desconocen como subrutina de amplificación de amplitud fundamental.

La rutina general ( `AmpAmpObliviousByReflectionPhases` ) tiene dos registros a los que llamamos `ancillaRegister` y `systemRegister` . También acepta dos Oracle para las reflexiones necesarias. `ReflectionOracle`Actúa solo en el `ancillaRegister` mientras que `ObliviousOracle` actúa conjuntamente en ambos registros. La entrada a `ancillaRegister` debe inicializarse en un eigenstate-1 del primer operador de reflexión $ \boldone-2P_1 $.

Normalmente, Oracle prepara el estado en la base de cálculo $ \ket{0...0} $. En nuestra implementación, `ancillaRegister` consta de un qubit ( `flagQubit` ) que controla `stateOracle` y el resto de los ancillas deseados. `stateOracle`Se aplica cuando `flagQubit` es $ \ket {1} $.

También puede proporcionar Oracle `StateOracle` y `ObliviousOracle` en lugar de reflexiones a través de una llamada a `AmpAmpObliviousByOraclePhases` .

Como se mencionó, la amplificación de amplitud tradicional es simplemente un caso especial de estas rutinas, donde `ObliviousOracle` es el operador de identidad y no hay ningún qubits del sistema (es decir, `systemRegister` está vacío). Si desea obtener fases para las reflexiones parciales (por ejemplo, para la búsqueda de Grover), la función `AmpAmpPhasesStandard` está disponible. Consulte `DatabaseSearch.qs` para obtener una implementación de ejemplo del algoritmo de Grover.

Se relacionan las fases de rotación de un solo qubit con las fases del operador de reflexión tal y como se describe en el documento [G.H. Low, i. L. Chuang](https://arxiv.org/abs/1707.05391). Las fases de punto fijo que se usan se detallan en [Yoder, Low y Chuang](https://arxiv.org/abs/1409.3305) junto con las fases en [Low, Yoder y Chuang](https://arxiv.org/abs/1603.03996).

Para el fondo, puede empezar a partir de la [amplificación de amplitud estándar](https://arxiv.org/abs/quant-ph/0005055) y pasar a una introducción a la [amplificación de amplitud desconocen](https://arxiv.org/abs/1312.1414) y, por último, generalizaciones presentadas en [Low y Chuang](https://arxiv.org/abs/1610.06546). [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf)proporcionó una presentación de información general interesante de todo este área (en relación con la simulación de Hamiltonian).

## <a name="quantum-fourier-transform"></a>Transformación de Fourier de Quantum ##

La transformación de Fourier es una herramienta fundamental del análisis clásico y es tan importante para los cálculos de Quantum.
Además, la eficacia de la *transformación de Fourier de Quantum* (QFT) supera en última medida lo que es posible en un equipo clásico que la convierte en una de las primeras herramientas que se pueden elegir al diseñar un algoritmo Quantum.

Como generalización aproximada de QFT, proporcionamos la <xref:microsoft.quantum.canon.approximateqft> operación que permite más optimizaciones mediante la eliminación de las rotaciones que no son estrictamente necesarias para la precisión algorítmica deseada.
El QFT aproximado requiere la operación Dyadic $Z $-Rotation <xref:microsoft.quantum.intrinsic.rfrac> , así como la <xref:microsoft.quantum.intrinsic.h> operación.
Se supone que la entrada y la salida se codifican en big endian codificación---es decir, qubit con el índice `0` se codifica en el bit más a la izquierda (más alto) de la representación de entero binario.
Esto se alinea con la [notación les](xref:microsoft.quantum.concepts.dirac), como un registro de tres qubits en el estado $ \ket {100} $ corresponde a $q _0 $ está en el estado $ \ket {1} $ mientras $q _ 1 _ 1 y $q _2 $ están en el estado $ \ket {0} $.
El parámetro de aproximación $a $ determina el nivel de eliminación de los $Z $-rotations, es decir, $a \en [0.. n] $.
En este caso, todos los $Z los giros $2 \ pi/2 ^ k $, donde $k > se quita un $ del circuito QFT.
Se sabe que para $k \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3. uno puede enlazar $ \\ | \operatorname{QFT}-\operatorname{AQFT} \\ | < \epsilon $.
Aquí $ \\ | \cdot \\ | $ es la norma de operador, que en este caso es la raíz cuadrada de la [eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced) mayor de $ (\operatorname{QFT}-\operatorname{AQFT}) (\operatorname{QFT}-\operatorname{AQFT}) ^ \dagger $.

## <a name="arithmetic"></a>Aritméticos ##

Al igual que las operaciones aritméticas desempeñan un papel fundamental en la informática clásica, también es indispensable en la informática Quantum.  Los algoritmos como el algoritmo de factorización de mé, los métodos de simulación Quantum y muchos algoritmos Oracular se basan en operaciones aritméticas coherentes.  La mayoría de los enfoques a la compilación aritmética sobre los circuitos de agregación de Quantum.  El agregador más sencillo toma una entrada clásica $b $ y agrega el valor a un estado Quantum que contiene un entero $ \ket{a} $.  Matemáticamente, el agregador (que denotamos $ \operatorname{Add} (b) $ para la entrada clásica $b $) tiene la propiedad que

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Este circuito de agregación básica es más un incrementador que un agregador.
Se puede convertir en un agregador que tiene dos entradas Quantum a través de $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b}, $ $ usando $n $ aplicaciones controladas de los agregadores con el formato \begin{align} \operatorname{Add} \ket{a} \ket{b} & = \Lambda \_ {a \_ 0} \Left (\operatorname{Add} (1) \Right) \Lambda \_ {a \_ 1} \left (\operatorname{Add} (2) \right) \Lambda \_ {a \_ 2} \left (\operatorname{Add} (4) \right) \cdots \Lambda \_ {a \_ {n-1}} \left (\operatorname{Add} ({{n-1}}) \right) \ket{a}\ket{b} \\ \\ & = \ket{a} \ket{b + a}, \end{align} para $n enteros de $-bit $a $ y $b $ y el módulo de suma $2 ^ n $.  Recuerde que la notación $ \Lambda \_ x (A) $ hace referencia, para cualquier operación $A $, a la versión controlada de esa operación con el control $x qubit $ as.

Del mismo modo, la multiplicación controlada por clases (un formato modular de que es esencial para el algoritmo de factorización de mé) se puede realizar mediante una serie similar de adiciones controladas: \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda \_ {x \_ 0} \Left (\operatorname{Add} (2 ^ 0 a) \Right) \Lambda \_ {a \_ 1} \left (\operatorname{Add} (2 ^ 1A) \right) \Lambda \_ {a \_ 2} \left (\operatorname{Add} (2 ^ 2 a) \right) \cdots \Lambda \_ {x \_ {n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\ \\ & = \ket{x}\ket{b + AX}.
\end{align} hay un sutileza con la multiplicación en los equipos Quantum que puede observar a partir de la definición de $ \operatorname{Mult} $ anterior.  A diferencia de la adición, la versión Quantum de este circuito almacena el producto de las entradas en un registro auxiliar en lugar de en el registro de entrada.  En este ejemplo, el registro se inicializa con el valor $b $, pero normalmente empezará a contener el valor cero.  Esto es necesario en porque, en general, no hay un inverso multiplicativo para el $a general $ y $x $.  Dado que todas las operaciones Quantum, Save Measurement, son reversibles, es necesario mantener suficiente información para invertir la multiplicación.  Por esta razón, el resultado se almacena en una matriz independiente.  Este truco para guardar la salida de una operación irreversible, como la multiplicación, en un registro independiente se conoce como "Bennett" después de Carlos Bennett y es una herramienta fundamental en la informática reversible y Quantum.

Muchos circuitos Quantum se han propuesto para su adición y cada uno de ellos explora un equilibrio diferente en cuanto al número de qubits (espacio) y el número de operaciones de puerta (tiempo) necesarias.  Revisamos dos agregadores eficientes de gran espacio que se indican a continuación, que se conocen como el agregador de Draper y el agregador de Beauregard.

### <a name="draper-adder"></a>Agregador de Draper ###

El agregador de Draper es posiblemente uno de los agregadores de Quantum más elegantes, ya que invoca directamente las propiedades Quantum para realizar la adición.  La información que se encuentra detrás del agregador de Draper es que la transformación de Fourier se puede usar para traducir los turnos de fase en un desplazamiento de bits.  Después, después de aplicar una transformación de Fourier, aplicar los turnos de fase adecuados y, a continuación, deshacer la transformación de Fourier, puede implementar un agregador.  A diferencia de muchos otros agregadores propuestos, el agregador de Draper usa explícitamente los efectos de Quantum introducidos a través de la transformación de Fourier de Quantum.  No tiene un homólogo natural natural.  A continuación se proporcionan los pasos específicos del agregador de Draper.

Supongamos que tiene dos $n qubit de $-bit que almacenan los enteros $a $ y $b $, para todos los $a $ $ $ \operatorname{QFT}\ket{a} = \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AJ)/2 ^ n} \ket{j}.
$ $ Si definimos $ $ \ket{\phi \_ k (a)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi a/2 ^ k} \ket {1} \right), $ $ después de algún álgebra puede ver que $ $ \operatorname{QFT}\ket{a} = \ket{\phi \_ 1 (a)} \otimes \cdots \otimes \ket{\phi \_ n (a)}.
$ $ La ruta de acceso hacia la realización de un agregador se vuelve clara después de observar que la suma de las entradas se puede escribir como $ $ \ket{a + b} = \operatorname{QFT} ^ {-1} \ket{\phi \_ 1 (a + b)} \otimes \cdots \otimes \ket{\phi \_ n (a + b)}.
$ $ Los enteros $b $ y $a $ se pueden agregar al realizar una rotación de fase controlada en cada una de las qubits de la descomposición usando los bits de los controles $b $ as.

Esta expansión se puede simplificar aún más indicando que para cualquier entero $j $ y el número real $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Esto se debe a que si gira $360 ^ {\circ} $ degrees ($ 2 \ PI $ radianes) en un círculo, acabará exactamente donde comenzó.  La única parte importante de $x $ para $e ^ {i2\pi x} $ es, por lo tanto, la parte fraccionaria de $x $.  En concreto, si tenemos una expansión binaria con el formato $x = y +0. x \_ 0x \_ 2 \ ldots x \_ n $ then $e ^ {i2\pi x} = e ^ {i2\pi (0. x \_ 0x \_ 2 \ ldots x \_ {n-1})} $ y, por tanto, $ $ \ket{\phi \_ k (a + b)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi [a/2 ^ k +0. b \_ K\ldots b \_ 1]} \ket {1} \right). $ $ Esto significa que, si se realiza una adición incrementando cada uno de los factores tensores en la expansión de la transformación de Fourier de $ \ket{a} $, el número de giros se reduce como $k $ reduce.  Esto reduce considerablemente el número de puertas de Quantum necesarias en el agregador.  Denotamos los pasos transformación de Fourier, adición de fase y transformación de Fourier inversa que conforman el agregador de Draper como $ \operatorname{QFT} ^ {-1} \left (\Phi \\ \! \operatorname{Add}\right) \operatorname{QFT} $. A continuación, se puede observar un circuito de Quantum que usa esta simplificación para implementar todo el proceso.

![El agregador de Draper se muestra como diagrama de circuito](~/media/draper.svg)

Cada puerta controlada $e ^ {I2 \ PI/k} $ del circuito hace referencia a una puerta de fase controlada.  Estas puertas tienen la propiedad que en el par de qubits en el que actúan, $ \ket {00} \mapsto \ket {00} $ pero $ \ket {11} \mapsto e ^ {I2 \ PI/k} \ les {11} $.  Este circuito nos permite realizar adiciones sin qubits adicionales, aparte de las necesarias para almacenar las entradas y las salidas.

### <a name="beauregard-adder"></a>Agregador de Beauregard ###

El agregador de Beauregard es un agregador modular de Quantum que usa el agregador de Draper para realizar el módulo de suma $N $ para un entero positivo de valor arbitrario $N $.  La importancia de los agregados modulares Quantum, como el agregador de Beauregard, se deriva en gran medida de su uso en el paso de exponenciación modular dentro del algoritmo de mé para la factorización.  Un agregador modular Quantum tiene la siguiente acción para la entrada Quantum $ \ket{b} $ y la entrada clásica $a $, donde $a $ y $b $ se promete que sean enteros mod $N $, lo que significa que se encuentran en el intervalo $ [0, \ldots, N-1] $.

$ $ \ket{b}\rightarrow \ket{b + a \text{mod} N} = \begin{Cases} \ket{b + a}, & b + a < N \\ \\ \ket{b + a-N}, & (b + a) \ge N \end{cases}.
$$

El agregador de Beauregard usa el agregador de Draper, o más específicamente $ \phi \\ \! \operatorname{Add} $, para agregar $a $ y $b $ en la fase.  A continuación, usa la misma operación para identificar si $a + b <N $ restando $N $ y prueba si $a + b-N<$0.  El circuito almacena esta información en un qubit auxiliar y, a continuación, agrega $N $ al registro si $a + b<N $.  A continuación, concluye descalculando este bit auxiliar (este paso es necesario para asegurarse de que se puede anular la asignación de ancilla después de llamar al agregador).  A continuación se proporciona el circuito del agregador de Beauregard.

![El agregador de Beauregard se muestra como diagrama de circuito](~/media/beau.svg)

Aquí, la puerta $ \Phi \\ \! \operatorname{Add} $ tiene el mismo formato que $ \Phi \\ \! \operatorname{Add} $, salvo que en este contexto la entrada es clásica en lugar de Quantum.  Esto permite reemplazar las fases controladas en $ \Phi \\ \! \operatorname{Add} $ por las puertas de fase que se pueden compilar en menos operaciones para reducir el número de qubits y el número de puertas necesarias para el agregador.

Para obtener más información, consulte [M. Roetteler, TH. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) y [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Estimación de fase cuántica ###

Una aplicación especialmente importante de la transformación de Fourier de Quantum es obtener información sobre los vectores propios de los operadores unitarios, un problema conocido como *estimación de fase*.
Considere la posibilidad de una $U unitario $ y un estado $ \ket{\phi} $, de modo que $ \ket{\phi} $ sea un eigenstate de $U $ con Unknown eigenvalue $ \phi $, \begin{Equation} U\ket {\ Phi} = \phi\ket{\phi}.
\end{Equation} si solo tenemos acceso a $U $ como Oracle, podremos obtener información sobre la fase $ \phi $ mediante el uso de que $Z $ rotaciones aplicadas al destino de una operación controlada se propagan de nuevo al control.

Supongamos que $V $ es una aplicación controlada de $U $, de modo que \begin{align} V (\ket {0} \otimes \ket{\phi}) & = \ket {0} \otimes \ket{\phi} \\ \\ \textrm{and} V (\ket {1} \otimes \ket{\phi}) & = e ^ {i \phi} \ket {1} \otimes \ket{\phi}.
\end{align}, por linearity, \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{(\ket {0} \otimes \ket{\phi}) + e ^ {i \phi} (\ket {1} \otimes \ket{\phi})} {\sqrt {2} }.
\end{align} podemos recopilar términos para encontrar que \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \frac{\ket {0} + e ^ {i \phi} \ket {1} } {\sqrt {2} } \otimes \ket{\phi} \\ \\ & = (R_1 (\phi) \ket{+}) \otimes \ket{\phi}, \end{align} donde $R _ _ 1 es la unitario aplicada por la <xref:microsoft.quantum.intrinsic.r1> operación.
Y se colocan de forma diferente, el efecto de aplicar $V $ es precisamente el mismo que aplicar $R _ 1 _ 1 con un ángulo desconocido, aunque solo se tiene acceso a $V $ como Oracle.
Por lo tanto, en el resto de este debate se tratará la estimación de fases en términos de $R _ 1 (\phi) $, que se implementan mediante el uso de la *fase Kickback*.

Dado que el registro de destino y el control permanecen inalterados después de este proceso, podemos volver a usar $ \ket{\phi} $ como destino de una aplicación controlada de $U ^ $2 para preparar un segundo control qubit en el estado $R _ 1 (2 \phi) \ket{+} $.
Continuando de este modo, podemos obtener un registro con el formato \begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \phi) \ket{+} \\ \\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket {0} + \exp (i 2 ^ {j} \phi) \ket {1} \right) \\ \\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{align} donde $n $ es el número de bits de precisión que se requiere. y donde hemos usado $ {} \propto {} $ para indicar que hemos suprimido el factor de normalización de $1/\sqrt{2 ^ n} $.

Si damos por hecho que $ \phi = 2 \pi p/2 ^ k $ para un entero $p $, se reconocerá como $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, donde $p _j $ es el $j ^ {\textrm{TH}} $ bit de $2 \pi \phi $.
Al aplicar el contiguo de la transformación de Fourier de Quantum, se obtiene la representación binaria de la fase codificada como estado de Quantum.

En Q# , esto lo implementa la <xref:microsoft.quantum.characterization.quantumphaseestimation> operación, que toma una <xref:microsoft.quantum.oracles.discreteoracle> aplicación de implementación de $U ^ m $ como una función de enteros positivos $m $.
