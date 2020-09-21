---
Título: Quantum Computing Glossary Description: un glosario de términos comunes, acciones y objetos que se usan en la informática Quantum.
Autor: bradben ms. Author: v-benbra ms. Date: 9/1/2020 ms. topic: artículo UID: Microsoft. Quantum. Glossary no-LOC:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="quantum-computing-glossary"></a>Glosario de Quantum Computing

## <a name="adjoint"></a>Contiguo

La transposición de conjugada compleja de una [operación](xref:microsoft.quantum.glossary#operation). En el caso de las operaciones que implementan un operador [unitario](xref:microsoft.quantum.glossary#unitary-operator) , el signo contiguo es el inverso de la operación y se indica mediante un símbolo Cruz. Por ejemplo, si la operación `U` representa el operador unitario $ u $ , `Adjoint U` representa $ u ^ \dagger $ . Para obtener más información, [vea el](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="ancilla"></a>Ancilla

Un [qubit](xref:microsoft.quantum.glossary#qubit) que actúa como memoria temporal para un equipo Quantum y que se asigna y se anula la asignación según sea necesario.  Para obtener más información, vea [varios qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Estado de campana

Uno de los cuatro Estados de [entangled](xref:microsoft.quantum.glossary#entanglement) [Quantum](xref:microsoft.quantum.glossary#quantum-state) con un estado máximo de dos qubits. Los cuatro Estados se definen $ \ket { \beta _ { ij } } = ( \mathbb { I } \otimes X ^ iz ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Un estado de campana también se conoce como un [par de EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Esfera Bloch

Representación gráfica de un [Estado de cuanto](xref:microsoft.quantum.glossary#quantum-state) de un solo[qubit](xref:microsoft.quantum.glossary#qubit) como punto en una esfera de unidad tridimensional. Para obtener más información, vea  [visualizar qubits y transformaciones mediante la esfera Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Llamadas

[Operación](xref:microsoft.quantum.glossary#operation) o [función](xref:microsoft.quantum.glossary#function) en el Q# lenguaje. Para obtener más información, vea [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="clifford-group"></a>Grupo Clifford

Conjunto de operaciones que ocupan el octants de la [esfera Bloch](xref:microsoft.quantum.glossary#bloch-sphere) y las permutaciones de efecto de los [operadores Pauli](xref:microsoft.quantum.glossary#pauli-operators). Entre ellas se incluyen las operaciones [ $ X $ ](xref:microsoft.quantum.intrinsic.x), [ $ y $ ](xref:microsoft.quantum.intrinsic.y), [ $ Z $ ](xref:microsoft.quantum.intrinsic.z), [ $ H $ ](xref:microsoft.quantum.intrinsic.h) y [ $ S $ ](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Regula

Una [operación](xref:microsoft.quantum.glossary#operation) Quantum que toma uno o más [qubits](xref:microsoft.quantum.glossary#qubit) como habilitadores para la operación de destino. Para obtener más información, vea [operaciones de control y de datos contiguos](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="dirac-notation"></a>Notación Dirac

Una abreviatura simbólica que simplifica la representación de [los Estados de Quantum](xref:microsoft.quantum.glossary#quantum-state), también denominada notación *bra-les* .  La parte *Bra* representa un vector de fila, por ejemplo, un $ \bra { 1 _ } = \begin{bmatrix} { 1 a un } & { _2 } \end{bmatrix} $ y la parte *les* representa un vector de columna b b _ $ \ket { 1 _ } = \begin{bmatrix} { 1 } \\\\ { _2 } \end{bmatrix} $ . Para obtener más información, consulte [notación Dirac](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

Factor por el que la aplicación de la transformación cambia el tamaño de una [Eigenvector](xref:microsoft.quantum.glossary#eigenvector) de una transformación determinada.  Dada una matriz cuadrada $ M $ y una Eigenvector $ v $ , entonces $ MV = CV $ , donde $ c $ es el eigenvalue y puede ser un número complejo de cualquier argumento. Para obtener más información, vea [conceptos de matriz avanzada](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

Vector cuya dirección no cambia en una transformación determinada y cuya magnitud cambia por un factor que corresponde a [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)de ese vector. Dada una matriz cuadrada $ M $ y una eigenvalue $ c $ , entonces $ MV = CV $ , donde $ v $ es un Eigenvector de la matriz y puede ser un número complejo de cualquier argumento. Para obtener más información, vea [conceptos de matriz avanzada](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Entrelazamiento

Las partículas Quantum, como [qubits](xref:microsoft.quantum.glossary#qubit), pueden estar conectadas o *desenredadas* de modo que no se puedan describir de forma independiente entre sí. Los resultados de la medición se correlacionan incluso cuando se separan infinitamente. La inenredo es esencial para [medir](xref:microsoft.quantum.glossary#measurement) el [Estado](xref:microsoft.quantum.glossary#quantum-state) de un qubit.  Para obtener más información, vea [conceptos de matriz avanzada](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>Par de EPR

Uno de los cuatro Estados de Quantum con un [Estado](xref:microsoft.quantum.glossary#quantum-state) máximo de dos [qubits](xref:microsoft.quantum.glossary#qubit). Los cuatro Estados se definen $ \ket { \beta _ { ij } } = ( \mathbb { 1 } \otimes X ^ iz ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Un par de EPR también se conoce como [Estado de campana](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Calidad

Cómo cambia el estado de un [Quantum](xref:microsoft.quantum.glossary#quantum-state) con el tiempo. Para obtener más información, consulte la [matriz exponencial](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Función
Tipo de subrutina en el Q# lenguaje que es puramente clásico (no Quantum). Mientras que las funciones se usan en los algoritmos Quantum, no pueden actuar en [las operaciones](xref:microsoft.quantum.glossary#operation) [qubits](xref:microsoft.quantum.glossary#qubit) o Call. Para obtener más información, vea [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="gate"></a>Canaliza

Un término heredado para una [operación](xref:microsoft.quantum.glossary#operation)Quantum, basado en el concepto de las puertas lógicas clásicas. Un [circuito Quantum](xref:microsoft.quantum.glossary#quantum-circuit-diagram) es una red de puertas (u operaciones), basada en el concepto similar de los circuitos lógicos de lógica.

## <a name="global-phase"></a>Fase global

Cuando dos [Estados](xref:microsoft.quantum.glossary#quantum-state) son idénticos a un múltiplo de un número complejo $ e ^ { i \phi } $ , se dice que se diferencian en una fase global. A diferencia de las fases locales, las fases globales no se pueden observar a través de cualquier [measurment](xref:microsoft.quantum.glossary#measurement). Para obtener más información, consulte [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

La operación Hadamard (a la que también se hace referencia como la puerta Hadamard o la transformación) actúa en una sola [qubit](xref:microsoft.quantum.glossary#qubit) y la coloca en una [superposición](xref:microsoft.quantum.glossary#superposition) uniforme de $ \ket { 0 } $ ó $ \ket { 1 } $ si la qubit está inicialmente en el $ \ket { } $ estado 0. En Q# , esta operación se aplica mediante la operación predefinida [`H`](xref:microsoft.quantum.intrinsic.h) .

## <a name="immutable"></a>Inmutable

Variable cuyo valor no se puede cambiar. Una variable inmutable en Q# se crea con la `let` palabra clave. Para declarar las variables que se *pueden* cambiar, use la palabra clave [mutable](xref:microsoft.quantum.glossary#immutable) para declarar y la `set` palabra clave para modificar el valor. 

## <a name="measurement"></a>Medición

Una manipulación de un [qubit](xref:microsoft.quantum.glossary#qubit) (o un conjunto de qubits) que produce el resultado de una observación, en efecto obtener un bit clásico. Para obtener más información, consulte [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Mutable

Variable cuyo valor se puede cambiar una vez creado. Una variable mutable en Q# se declara mediante la `mutable` palabra clave y se modifica mediante la `set` palabra clave. Las variables creadas con la `let` palabra clave son [inmutables](xref:microsoft.quantum.glossary#immutable) y su valor no se puede cambiar.

## <a name="namespace"></a>Espacio de nombres

Etiqueta para una colección de nombres relacionados (es decir, [operaciones](xref:microsoft.quantum.glossary#operation), [funciones](xref:microsoft.quantum.glossary#function)y [tipos definidos por el usuario](xref:microsoft.quantum.glossary#user-defined-type)). Por ejemplo, el espacio de nombres [Microsoft. Quantum. preparación](xref:microsoft.quantum.preparation) etiqueta todos los símbolos definidos en la biblioteca estándar que ayudan a preparar los Estados iniciales.

## <a name="operation"></a>Operación

Unidad básica del cálculo de Quantum en Q# . Es aproximadamente equivalente a una función de C, C++ o Python, o a un método estático en C# o Java. Para obtener más información, vea [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="operator-application"></a>Operador Application

Realización de una operación Quantum. Normalmente, esto aplica una matriz de unitarios al vector de estado de Quantum actual.

## <a name="oracle"></a>Oracle

Subrutina que proporciona información dependiente de datos a un algoritmo Quantum en tiempo de ejecución. Normalmente, el objetivo es proporcionar una [superposición](xref:microsoft.quantum.glossary#superposition) de salidas que corresponden a las entradas que están en posición de superposición. Para obtener más información, vea [Oracle](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Aplicación parcial

Llamar a una [función](xref:microsoft.quantum.glossary#function) u [operación](xref:microsoft.quantum.glossary#operation) sin todas las entradas necesarias. Esto devuelve un nuevo [llamador](xref:microsoft.quantum.glossary#callable) que solo necesita los parámetros que faltan (indicados por un carácter de subrayado) para que se proporcionen durante una aplicación futura. Por ejemplo, dada la función, `MyFunc(x : int, y : int) : int {return x + y;}` se puede aplicar parcialmente a una nueva función `let NewFunc = MyFunc(_, 3)` . Después, puede llamar a la nueva función más adelante con el parámetro que falta, `NewFunc(2)` que devuelve el valor *5*.  Para obtener más información, vea [aplicación parcial](xref:microsoft.quantum.guide.operationsfunctions#partial-application).

## <a name="pauli-operators"></a>Operadores Pauli

Un conjunto de tres matrices unitarios de 2 x 2 conocidas como las `X` `Y` operaciones, y `Z` Quantum. La matriz de identidad, $ I $ , suele incluirse también en el conjunto.  $I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix} $ , $ X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} $ , $ y = \begin{bmatrix} 0 & -i \\\\ i & \end{bmatrix} $ , $ Z = \begin{bmatrix} 1 & 0 0 \\\\ & -1 \end{bmatrix} $ .   Para obtener más información, consulte [operaciones de un solo qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagrama del circuito de Quantum

Un método para representar gráficamente la secuencia de [operaciones](xref:microsoft.quantum.glossary#operation) (o [puertas](xref:microsoft.quantum.glossary#gate)) para programas Quantum simples, por ejemplo 

![Diagrama de circuitos de ejemplo](~/media/qpe.png). 

Para obtener más información, consulte los [circuitos de Quantum](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Bibliotecas de Quantum

Colecciones de [operaciones](xref:microsoft.quantum.glossary#operation), [funciones](xref:microsoft.quantum.glossary#function) y [tipos definidos por el usuario](xref:microsoft.quantum.glossary#user-defined-type) para crear Q# programas. La [biblioteca estándar](xref:microsoft.quantum.libraries.standard.intro) se instala de forma predeterminada. Otras bibliotecas disponibles son la biblioteca de [química](xref:microsoft.quantum.chemistry.concepts.intro), la [biblioteca de valores numéricos](xref:microsoft.quantum.numerics.intro) y la biblioteca de [machine learning](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Estado de Quantum

Estado preciso de un sistema de Quantum aislado, del que se pueden extraer las probabilidades de [medición](xref:microsoft.quantum.glossary#measurement) . En Quantum Computing, el simulador de Quantum usa esta información para simular el modo en que qubits responde a las operaciones. Para obtener más información, consulte [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Unidad básica de información de Quantum, análoga a un *bit* de la informática clásica. Para obtener más información, consulte [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Repetir hasta éxito

Un algoritmo Quantum que se ejecuta con probabilidad de éxito. En caso de error, la rutina volverá a intentarlo hasta que sea correcta (o se alcance un límite). Para obtener más información, consulte [repetir hasta éxito (RU)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) .

## <a name="standard-libraries"></a>Bibliotecas estándar

[Operaciones](xref:microsoft.quantum.glossary#operation), [funciones](xref:microsoft.quantum.glossary#function) y [tipos definidos por el usuario](xref:microsoft.quantum.glossary#user-defined-type) que se instalan junto con el Q# compilador durante la instalación. La implementación de la biblioteca estándar es independiente con respecto a los equipos de destino. Para obtener más información, vea [bibliotecas estándar](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Superposición

El concepto de Quantum Computing que [qubit](xref:microsoft.quantum.glossary#qubit) es una combinación lineal de dos Estados, $ \ket { 0 } $ y $ \ket { 1 } $ , hasta que se [mida](xref:microsoft.quantum.glossary#measurement).  Para obtener más información, vea Descripción de la [informática Quantum](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Máquina de destino

Un destino de compilación que reduce un programa Quantum abstracto hacia el hardware o la simulación. Esto suele incluir reescrituras para muchos propósitos, incluidos el reemplazo de la puerta, la codificación para la corrección de errores, el diseño geométrico y otros. Para obtener más información, consulte [simuladores Quantum y aplicaciones host](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportabilidad

Un método para volver a generar los datos, o el [Estado de Quantum](xref:microsoft.quantum.glossary#quantum-state), de un [qubit](xref:microsoft.quantum.glossary#qubit) de un lugar a otro sin mover físicamente el qubit, con el [inenredo](xref:microsoft.quantum.glossary#entanglement) y la [medición](xref:microsoft.quantum.glossary#measurement).  Para obtener más información, consulte los [circuitos Quantum](xref:microsoft.quantum.concepts.circuits) y los Kata respectivos en [Quantum katas](xref:microsoft.quantum.overview.katas).

## <a name="tuple"></a>Tuple

Colección de valores separados por comas que actúa como un valor único. El *tipo* de una tupla se define mediante los tipos de valores que contiene. En Q# , las tuplas son [inmutables](xref:microsoft.quantum.glossary#immutable) y se pueden anidar, contener matrices o usarse en una matriz. Para obtener más información, consulte [Tipos de tupla](xref:microsoft.quantum.guide.types#tuple-types).

## <a name="unitary-operator"></a>Operador unitario

Operador cuyo inverso es igual a su signo [contiguo](xref:microsoft.quantum.glossary#adjoint), es decir, $ UU ^ { \dagger } = \id $ .

## <a name="user-defined-type"></a>Tipo definido por el usuario

Colección de tipos integrados o definidos previamente que se pueden denominar una sola unidad. Para obtener más información, vea [tipos definidos por el usuario](xref:microsoft.quantum.guide.types#user-defined-types).