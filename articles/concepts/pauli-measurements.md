---
Título: Descripción de las medidas de Pauli: Aprenda a trabajar con operaciones de medición Pauli de un solo qubit.
Autor: QuantumWriter UID: Microsoft. Quantum. Concepts. Pauli ms. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 ms. topic: article no-LOC:
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

# <a name="pauli-measurements"></a>Medidas Pauli

En las conversaciones anteriores, nos hemos centrado en las mediciones de base de cálculo.
De hecho, hay otras medidas comunes que se producen en la informática Quantum que, desde una perspectiva de notación, son convenientes para expresar en términos de mediciones de base de cálculo.
A medida que trabaje con Q# , el tipo más común de medidas en las que se ejecutará probablemente serán *mediciones Paulis*, que generalizan las mediciones de base de cálculo para incluir medidas en otras bases y de paridad entre diferentes qubits.
En tales casos, es habitual analizar un operador Pauli, en general un operador como $ X, Y, z $ o $ z \otimes z, x \otimes x, x y \otimes , etc $ .

> [!TIP]
>En Q# , los operadores de Pauli de varios qubit suelen estar representados por matrices de tipo `Pauli[]` .
>Por ejemplo, para representar $ X \otimes Z \otimes Y $ , puede usar la matriz `[PauliX, PauliZ, PauliY]` .

La explicación de la medida en términos de operadores Pauli es especialmente común en el subcampo de la corrección de errores Quantum.
En Q# , seguimos una Convención similar; ahora explicaremos esta vista alternativa de las medidas.

Antes de profundizar en los detalles de cómo pensar en una medición Pauli, es útil pensar en qué medida un qubit único dentro de un equipo Quantum se realiza en el estado de Quantum.
Imagine que tenemos un $ $ Estado de Quantum n-qubit; después, la medición de una qubit de inmediato pone a la mitad de las $ 2 ^ n $ posibilidades de que el Estado pudiera estar en.
En otras palabras, la medida proyecta el estado de cuanto en uno de los dos espacios a medio.
Podemos generalizar el modo en que pensamos en medida para reflejar este Intuition.

Para identificar de manera concisa estos subespacios, necesitamos un lenguaje para describirlos.
Una manera de describir los dos subespacios es mediante la especificación de una matriz que solo tiene dos vectores propios únicos, tomadas por Convención para que sea $ \pm 1 $ .
Para obtener un ejemplo sencillo de la descripción de los subespacios de esta manera, considere $ Z $ :

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} .
\end{align}
$$

Al leer los elementos diagonales de la matriz Pauli- $ z $ , podemos ver que $ Z $ tiene dos vectores propios, $ \ket { 0 } $ y $ \ket { 1 } $ , con vectores propios $ \pm 1 correspondiente $ .
Por lo tanto, si se mide el qubit y se obtiene `Zero` (correspondiente al estado $ \ket { 0 } $ ), sabemos que el estado de nuestro qubit es un $ eigenstate + 1 $ del $ $ operador Z.
Del mismo modo, si obtenemos `One` , sabemos que el estado de nuestro qubit es $ -1 $ eigenstate de $ Z $ . Este proceso se conoce en el idioma de las medidas de Pauli como "medición de Pauli $ Z $ " y es totalmente equivalente a realizar una medición de base de cálculo.

Cualquier $ \times matriz 2 2 $ que sea una transformación unitario de $ Z $ también cumple este criterio.
Es decir, también podríamos usar una matriz u $ = ^ \dagger Z u $ , donde $ U $ es cualquier otra matriz de unidades unitarios, para proporcionar una matriz que defina los dos resultados de una medida en su $ \pm 1 $ vectores propios.
La notación de las medidas Pauli hace referencia a esta equivalencia de unitarios mediante la identificación de las $ medidas X, Y, Z $ como medidas equivalentes que puede hacer para obtener información de un qubit.
Estas medidas se proporcionan a continuación para mayor comodidad.


|Pauli | transformación unitario de medida|
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X | $H               $                    |
|$ $ Y | $Hs ^               {\dagger}$         |

Es decir, con este lenguaje, "Measure $ Y $ " es equivalente a aplicar $ HS ^ \dagger $ y luego medir en función del cálculo, donde [`S`](xref:microsoft.quantum.intrinsic.s) es una operación de Quantum intrínseca que a veces se denomina "puerta de fase" y se puede simular mediante la matriz de la unidad de medida.

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} .
\end{align}
$$

También es equivalente a aplicar $ HS ^ \dagger $ al vector de estado de Quantum y después medir $ Z $ , de modo que la operación siguiente sea equivalente a `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

A continuación, se encontraría el estado correcto transformando de nuevo a la base de cálculo, que equivale a aplicar $ SH $ al vector de estado de Quantum; en el fragmento de código anterior, la transformación de vuelta a la base de cálculo se controla automáticamente mediante el uso del `within … apply` bloque.

En Q# , se indica el resultado---es decir, la información clásica extraída de la interacción con el estado---se proporciona mediante un `Result` valor $ j \in \\ { \texttt { cero } , \texttt { uno } \\ } $ que indica si el resultado está en el $ (-1) ^ j $ eigenspace del operador Pauli medido.


## <a name="multiple-qubit-measurements"></a>Mediciones de varios qubit

Las medidas de los operadores qubit de Pauli se definen de forma similar, como se aprecia en:

$$
Z \otimes z = \begin{bmatrix} 1 & 0 & 0 0 0 & \\\\ & -1 & 0 & 0 0 0 \\\\ & & -1 0 0 0 & \\\\ & & & 1 \end{bmatrix} .
$$

Por lo tanto, los productos tensores de dos operadores Pauli- $ Z $ forman una matriz formada por dos espacios compuestos de $ + 1 $ y $ -1 $ vectores propios.
Al igual que en el caso de un solo qubit, ambos constituyen un medio de espacio, lo que significa que la mitad del espacio de vector accesible pertenece a la $ eigenspace + 1 $ y la mitad restante al $ eigenspace-1 $ .
En general, es fácil ver a partir de la definición del producto tensores que cualquier producto tensores de los operadores Pauli- $ Z $ y la identidad también obedece esto.
Por ejemplo,

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 & 0 & 0 0 &\\\\
        0 & 1 & 0 & 0\\\\
        0 & 0 & -1 & 0\\\\
        0 0 0 & & & -1 \end{bmatrix} .
\end{align}
$$

Como antes, cualquier transformación unitario de estas matrices también describe dos espacios a la mitad etiquetados por $ \pm 1 $ vectores propios.
Por ejemplo, $ x \otimes x = h \otimes h (z \otimes z) h \otimes h $ de la identidad que $ Z = HxH $ .
Al igual que en el caso de una qubit, todas las medidas Pauli-qubit se pueden escribir como $ u ^ \dagger (Z \otimes \id ) u $ para $ 4 \times 4 $ matrices unitarios $ u $ . En la tabla siguiente se enumeran las transformaciones.

> [!NOTE]
>En la tabla siguiente, usamos $ \operatorname { swap } $ para indicar la matriz >$$
> \begin{align}
>     \operatorname{INTERCAMBIO } & de=
>     \left( \begin { matriz}
>1 & 0 & 0 0 &\\\\
>0 & 0 & 1 & 0\\\\
>0 & 1 & 0 & 0\\\\
>0 & 0 & 0 & 1 > \end { matriz } \right ) >     \end{align}
> $$
>se usa para simular la operación intrínseca [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Pauli | transformación unitario de medida|
|----------------------|------------------------|
|$ \otimes \boldone Z $ | $\boldone \otimes \boldone$|
|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|
|$ \otimes \boldone X $ | $ \otimes \boldone H $|
|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|
|$\boldone \otimes $ | $ \operatorname { intercambio } Z $|
|$\boldone \otimes $ | $ \otimes \boldone \operatorname { intercambio } X (H $ )|
|$\boldone \otimes s $ | $ (HS ^ \dagger \otimes \boldone ) \operatorname { swap } $|
|$Z \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } $|
|$X \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes \boldone ) $|
|$Y \otimes Z $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|
|$Z \otimes X $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes H) $|
|$X \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (h \otimes h) $|
|$Y \otimes X $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimes S $ | $ \operatorname { CNOT } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|
|$X \otimes Y $ | $ \operatorname { CNOT } \_ { 10 } (H \otimes HS ^ \dagger ) $|
|$Y \otimes S $ | $ \operatorname { CNOT } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|

En este caso, la [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operación aparece por el siguiente motivo.
Cada medida de Pauli que no incluya la $ \boldone $ matriz es equivalente a una unitario a $ z \otimes z $ por la razón anterior.
El vectores propios de $ z \otimes z $ solo depende de la paridad de la qubits que conforman cada vector de base de cálculo y las operaciones controladas no sirven para calcular esta paridad y almacenarla en el primer bit.
Después, una vez que se mide el primer bit, podemos recuperar la identidad del espacio medio resultante, que es equivalente a medir el operador Pauli.

Una nota adicional: aunque puede ser tentador asumir que la medida z $ \otimes z $ es la misma que la medición secuencial de $ z \otimes \mathbb { 1 } $ y, a continuación, $ \mathbb { 1 } \otimes z $ , esta suposición sería falsa.
La razón es que medir $ z \otimes z $ proyecta el estado de cuanto en el $ eigenstate + 1 $ o $ -1 $ de estos operadores.
$La medida \otimes \mathbb { de z 1 } $ y, a continuación, $ \mathbb { 1 } \otimes Z $ proyecta el vector de estado de Quantum primero en un espacio medio de $ Z \otimes \mathbb { 1 } $ y, a continuación, en un espacio medio de $ \mathbb { 1 } \otimes Z $ . Como hay cuatro vectores de base de cálculo, al realizar ambas mediciones se reduce el estado a un cuarto de espacio y, por tanto, se reduce a un vector de base de cálculo único.

## <a name="correlations-between-qubits"></a>Correlaciones entre qubits
Otra forma de ver los productos de tensores de matrices de Pauli como $ x \otimes x $ o $ z \otimes z $ es que estas medidas permiten examinar la información almacenada en las correlaciones entre las dos qubits.
$La medición \otimes \id $ de X permite examinar la información que se almacena localmente en el primer qubit.
Aunque ambos tipos de medidas son igualmente valiosos en la informática Quantum, el primero ilumina la potencia de la informática Quantum.
Revela que, con frecuencia, la información que desea aprender no se almacena en ningún qubit único, sino que se almacena de forma no local en todas las qubits a la vez y, por lo tanto, solo al examinarla a través de una medida conjunta (por ejemplo, $ z \otimes z $ ) hace que esta información se convierta en manifiesto.

Por ejemplo, en la corrección de errores, a menudo queremos obtener información sobre el error que se produjo al no aprender nada sobre el estado que estamos intentando proteger.
El [ejemplo de código bit-Flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) muestra un ejemplo de cómo puede hacerlo con medidas como $ z \otimes z \otimes \id $ y $ \id \otimes z \otimes z $ . < --TODO: cámbielo a un vínculo al explorador de ejemplos en cuanto se incorpora el ejemplo de código bit-flip. -->

$ \otimes \otimes \otimes \boldone $ También se pueden medir los operadores de Pauli arbitrarios como X Y Z.
Todos estos productos tensores de los operadores Pauli tienen solo dos vectores propios $ \pm 1 $ y ambos eigenspaces constituyen caracteres de medio ancho del espacio vectorial completo.
Por lo tanto, coinciden con los requisitos indicados anteriormente.

En Q# , tales mediciones devuelven $ j $ si la medida produce un resultado en el eigenspace de signo $ (-1) ^ j $ .
Tener medidas de Pauli como característica integrada en Q# es útil porque la medición de estos operadores requiere largas cadenas de puertas y transformaciones controladas no para describir la puerta U de la estructura de la diagonal $ $ necesaria para expresar la operación como un producto tensores de $ Z $ y $ \id $ .
Al poder especificar que desea realizar una de estas medidas predefinidas, no es necesario preocuparse por cómo transformar la base de forma que una medición de base de cálculo proporcione la información necesaria.
Q#controla todas las transformaciones de base necesarias automáticamente.
Para obtener más información, vea [`Measure`](xref:microsoft.quantum.intrinsic.measure) las [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operaciones y.

## <a name="the-no-cloning-theorem"></a>Teorema sin clonación

La información de Quantum es eficaz.
Nos permite hacer cosas sorprendentes, como números de factor exponencialmente más rápidos que los mejores algoritmos clásicos conocidos, o simular eficazmente sistemas de electrones correlacionados que requieran el costo exponencial para simular con precisión.
Sin embargo, existen limitaciones en cuanto a la eficacia de la informática Quantum.
Una de estas limitaciones viene determinada por el *teorema sin clonación*.

La teorema sin clonación tiene un nombre acertado.
No permite la clonación de Estados de Quantum genéricos por un equipo Quantum.
La prueba de Teorema es bastante sencilla.
Aunque una prueba completa del teorema sin clonación es un poco muy técnico para nuestro debate aquí, la prueba, en el caso de que no haya ningún qubits auxiliar adicional, se encuentra dentro de nuestro ámbito (los qubits auxiliares son qubits que se usan para el espacio de desecho durante un cálculo y se usan y administran fácilmente en Q# , vea [qubits prestado](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).

Para este tipo de equipo Quantum, la operación de clonación debe describirse mediante una matriz de unitario.
No permitimos la medición, ya que dañaría el estado de Quantum que estamos intentando clonar.
Para simular la operación de clonación, queremos que la matriz de unitarios se use para tener la propiedad que$$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
para cualquier estado $ \ket { \psi } $ .
La propiedad linearity de la multiplicación de matrices implica que, para cualquier segundo estado de Quantum $ \ket { \phi } $ ,

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}
    &= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).
\end{align}
$$

Esto proporciona el Intuition fundamental detrás del teorema sin clonación: cualquier dispositivo que copie un estado de Quantum desconocido debe inducir errores en al menos algunos de los Estados que copia.
Aunque la principal suposición de que el Cloner actúa de forma lineal en el estado de la entrada se puede infringir a través de la adición y medición de qubits auxiliares, estas interacciones también pierden información sobre el sistema a través de las estadísticas de medida y evitan la clonación exacta en estos casos.
Para obtener una prueba más completa de la teorema sin clonación, vea [para obtener más información](xref:microsoft.quantum.more-information).

La teorema sin clonación es importante para el conocimiento cualitativo de la informática Quantum, ya que si pudiera clonar los Estados de Quantum de forma económica, se le concederá una capacidad casi mágica para aprender de los Estados de Quantum.
En realidad, puede infringir el principio de incertidumbre de vaunted de Heisenberg.
Como alternativa, puede usar una Cloner óptima para tomar una muestra única de una distribución de Quantum compleja y obtener información sobre todo lo que podría obtener más información sobre esa distribución desde un solo ejemplo.
Esto sería similar a la forma de voltear una moneda y observar los cabezales y, a continuación, al decir a un amigo sobre el resultado de responder "Ah la distribución de esa moneda debe ser Bernoulli con $ p = 0.512643 \ ldots $ !".  Este tipo de instrucción sería no SENS, porque un bit de información (el resultado de los cabezales) simplemente no puede proporcionar los numerosos bits de información necesaria para codificar la distribución sin información importante de gran tamaño.
Del mismo modo, sin información previa, no se puede clonar absolutamente un estado de Quantum, al igual que no se puede preparar un conjunto de esas monedas sin conocer $ p $ .

La información no es gratuita en la informática Quantum.
Cada qubit medido proporciona un único bit de información y el teorema sin clonación muestra que no hay ninguna puerta trasera que pueda aprovecharse para evitar el equilibrio fundamental entre la información obtenida sobre el sistema y la perturbación invocada.
