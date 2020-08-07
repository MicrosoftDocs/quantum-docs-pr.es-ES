---
title: Quantum Oracle Description: Obtenga información sobre cómo trabajar con y definir las operaciones de Black Box que se usan como entrada en otro algoritmo.
Autor: cgranade UID: Microsoft. Quantum. Concepts. Oracle ms. Author: Christopher.Granade@microsoft.com MS. Date: 07/11/2018 ms. topic: article no-LOC:
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
# <a name="quantum-oracles"></a>Oracle Quantum

Una $ O Oracle $ es una operación de "caja negra" que se usa como entrada para otro algoritmo.
A menudo, estas operaciones se definen mediante una función clásica $ f: \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ que toma $ una $ entrada binaria de n bits y genera una $ $ salida binaria de m bits.
Para ello, considere una entrada binaria determinada $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .
Podemos etiquetar los Estados de qubit como $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .

En primer lugar, es posible que se intente definir $ o $ para que $ o \ket { x } = \ket { f (x) } $ , pero esto tiene un par de problemas.
En primer lugar, $ f $ puede tener un tamaño diferente de entrada y salida ( $ n \ne m $ ), de modo que $ la aplicación de O cambiaría $ el número de qubits en el registro.
En segundo lugar, incluso si $ n = m $ , es posible que la función no se pueda invertir: Si $ f (x) = f (y) $ para some $ x \ne y $ , entonces $ o \ket { x } = o \ket { y, } $ $ o ^ o \dagger \ket { x } \ne o ^ \dagger o \ket { y } $ .
Esto significa que no se puede crear la operación de "contiguo" $ o ^ y que las \dagger $ Oracle tienen que tener un método contiguo definido para ellos.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definir un Oracle por su efecto en Estados de base de cálculo
Podemos tratar estos dos problemas introduciendo un segundo registro de $ m $ qubits para mantener la respuesta.
A continuación, se definirá el efecto de Oracle en todos los Estados de base de cálculo: para todos los $ x \in \\ { 0, 1 \\ } ^ n $ e y $ \in \\ { 0, 1 \\ } ^ m $ ,

$$
\begin{align}
    O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .
\end{align}
$$

Ahora $ o = ^ \dagger $ por construcción, hemos resuelto ambos problemas anteriores.

> [!TIP]
>Para ver que $ o = ^ { \dagger } $ , tenga en cuenta que $ o ^ 2 = \boldone $ desde $ \oplus b \oplus b = a $ para todos $ a, b \in \: :: no-LOC ({)::: 0, 1 \: :: no-LOC (})::: $ .
>Como resultado, $ O \ket { x x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .

Lo importante es que la definición de Oracle de este modo para cada estado de base de cálculo $ \ket { x } \ket { y } $ también define cómo $ $ actúa O para cualquier otro Estado.
Esto se sigue inmediatamente desde el hecho de que $ O $ , al igual que todas las operaciones Quantum, es lineal en el estado en el que actúa.
Considere la operación Hadamard, por ejemplo, definida por $ h \ket { 0 } = \ket { + } $ y $ h \ket { 1 } = \ket { - } $ .
Si deseamos saber cómo $ funciona h $ $ \ket { + } $ , podemos usar que $ h $ es lineal,

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } H ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (H \ket { 0 } + h \ket { 1 } )\\\\
           &= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .
\end{align}
$$

En el caso de definir nuestra $ O Oracle $ , podemos usar de forma similar que cualquier estado $ \ket { \psi } $ en $ n + m $ qubits se puede escribir como

$$
\begin{align}
\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}
\end{align}
$$

donde $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ representa los coeficientes del estado $ \ket { \psi } $ . Así,

$$
\begin{align}
O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .
\end{align}
$$

## <a name="phase-oracles"></a>Oracle de fase
Como alternativa, podemos codificar $ f $ en Oracle $ O $ aplicando una _fase_ basada en la entrada a $ O $ . Por ejemplo, podríamos definir $ O $ tal que$$
\begin{align}
    O \ket { x } = (-1) ^ { f (x) } \ket { x } .
\end{align}
$$
Si una fase de Oracle actúa en un registro inicialmente en el estado x de la base de cálculo $ \ket { } $ , esta fase es una fase global y, por lo tanto, no observable.
Pero este tipo de Oracle puede ser un recurso muy eficaz si se aplica a una superposición o como una operación controlada.
Considere, por ejemplo, una fase $ de oracle O_f $ para una función de qubit única $ f $ .
A$$
\begin{align}
    O_f\ket{+}
        &=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\
        &=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .
\end{align}
$$

En general, se pueden ampliar ambas vistas de Oracle para representar funciones clásicas que devuelven números reales en lugar de un solo bit.

Elegir la mejor manera de implementar Oracle depende en gran medida de cómo se utilizará este Oracle dentro de un algoritmo determinado.
Por ejemplo, el [algoritmo Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) se basa en la implementación de Oracle en primer lugar, mientras que el [algoritmo de Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) se basa en Oracle implementado de la segunda manera.


Para obtener más detalles, se recomienda la explicación de [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
