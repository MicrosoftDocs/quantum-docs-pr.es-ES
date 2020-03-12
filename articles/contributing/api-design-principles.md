---
title: 'Principios de diseño de la API de Q #'
description: 'Principios de diseño de la API de Q #'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: 03c32331f8988181ec6fedcfc207d752b4a880b2
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024209"
---
# <a name="q-api-design-principles"></a>Principios de diseño de la API de Q #

## <a name="introduction"></a>Introducción

Como lenguaje y como plataforma, Q # permite a los usuarios escribir, ejecutar, comprender y explorar aplicaciones Quantum.
Con el fin de permitir a los usuarios, cuando diseñamos bibliotecas de preguntas y respuestas, seguimos un conjunto de principios de diseño de la API para guiarnos en nuestros diseños y para ayudarnos a hacer bibliotecas que se puedan usar para la comunidad de desarrollo de Quantum.
En este artículo se enumeran estos principios y se proporcionan ejemplos para ayudarle a aplicarlos al diseñar API de preguntas y respuestas.

> [!TIP]
> Se trata de un documento bastante detallado que está pensado para ayudar a guiar el desarrollo de la biblioteca y las contribuciones de la biblioteca en profundidad.
> Probablemente le resulte más útil si está escribiendo sus propias bibliotecas en Q # o si está aportando características más grandes al repositorio de las [bibliotecas de q #](https://github.com/microsoft/QuantumLibraries).
>
> Por otro lado, si desea obtener información sobre cómo contribuir al kit de desarrollo de Quantum de forma más general, se recomienda empezar por la [Guía de contribución](xref:microsoft.quantum.contributing).
> Si busca más información general sobre cómo se recomienda dar formato a su código de preguntas y respuestas, puede que le interese desproteger la [Guía de estilo](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Principios generales

**Principio clave:** Exponga las API que sitúan el foco en aplicaciones Quantum.

- ✅ **Elija** nombres de operación y función que reflejen la estructura de alto nivel de los algoritmos y las aplicaciones.
- ⛔️ **no** exponen las API que se centran principalmente en los detalles de implementación de bajo nivel.

**Principio clave:** Inicie cada diseño de API con casos de uso de ejemplo para asegurarse de que las API son intuitivas de usar.

- ✅ **asegurarse** de que cada componente de una API pública tiene un caso de uso correspondiente, en lugar de intentar diseñar todos los usos posibles desde el principio.
    Se colocan de forma diferente, no presentan API públicas en caso de que sean útiles, pero asegúrese de que cada una de las partes de una API tiene un ejemplo *concreto* en el que será útil.

  *Ejemplos:*
  - @"microsoft.quantum.canon.applytoeachca" puede usarse como `ApplyToEachCA(H, _)` para preparar los registros en un estado de superposición uniforme, una tarea común en muchos algoritmos Quantum. También se puede usar la misma operación para muchas otras tareas en la preparación, los valores numéricos y los algoritmos basados en Oracle.

- ✅ **realizar** un nuevo diseño de la API de Brainstorm and Workshop para comprobar que son intuitivos y cumplen los casos de uso propuestos.

  *Ejemplos:*
  - Inspeccione el código de Q\# actual para ver cómo los nuevos diseños de API pueden simplificar y aclarar las implementaciones existentes.
  - Revise los diseños de API propuestos con representantes de audiencias principales.

**Principio clave:** Diseñe las API para admitir y fomentar el código legible.

- ✅ asegurarse de que el código sea legible por expertos en el dominio **y no expertos** .
- ✅ **realizar** el foco en los efectos de cada operación y función en el algoritmo de alto nivel, utilizando la documentación para profundizar en los detalles de implementación, según corresponda.
- ✅ **siga** la guía de [estilo de Q\#](xref:microsoft.quantum.contributing.style) común siempre que proceda.

**Principio clave:** Diseñe las API para ser estables y proporcionar compatibilidad con versiones posteriores.

- ✅ **DO** descartar las API antiguas correctamente cuando se requieren cambios importantes.

- ✅ **proporcionan** operaciones y funciones "Shim" que permiten que el código de usuario existente funcione correctamente durante el desuso.

  *Ejemplos:*
  - Al cambiar el nombre de una operación llamada `EstimateExpectation` a `EstimateAverage`, se introduce una nueva operación denominada `EstimateExpectation` que llama a la operación original en su nuevo nombre, de modo que el código existente puede continuar funcionando correctamente.

- ✅ **usar** el atributo @"microsoft.quantum.core.deprecated" para comunicar los desuso al usuario.

- ✅ al cambiar el nombre de una operación o **función, proporcione** el nuevo nombre como entrada de cadena para `@Deprecated`.

- ⛔️ **no** Quite las funciones u operaciones existentes sin un período de desuso de al menos seis meses para las versiones preliminares, o al menos dos años para las versiones admitidas.

## <a name="functions-and-operations"></a>Funciones y operaciones

**Principio clave:** Asegúrese de que cada función y operación tiene un único propósito bien definido dentro de la API.

- ⛔️ **no** exponen funciones y operaciones que realizan varias tareas no relacionadas.

**Principio clave:** diseñe las funciones y operaciones para que sean lo más reutilizables posible y para prever las necesidades futuras.

- ✅ **realizar** funciones y operaciones de diseño para componerse bien con otras funciones y operaciones, tanto en la misma API como en las bibliotecas existentes anteriormente.

  *Ejemplos:*
  - La operación @"microsoft.quantum.canon.delay" hace suposiciones mínimas sobre su entrada y, por lo tanto, se puede usar para retrasar las aplicaciones de cualquiera de las dos operaciones en la biblioteca de Q # Standard o según lo definido por los usuarios.
    <!-- TODO: define bad example. -->

- ✅ **DO** exponen lógica clásica puramente determinista como funciones en lugar de operaciones.

  *Ejemplos:*
  - Una subrutina que recuadrada su entrada de punto flotante puede escribirse de forma determinista y, por tanto, debe exponerse al usuario como `Squared : Double -> Double` en lugar de como una operación `Square : Double => Double`. Esto permite llamar a la subrutina en más lugares (por ejemplo, dentro de otras funciones) y proporciona información de optimización útil al compilador que puede afectar al rendimiento y a las optimizaciones.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` y `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` difieren en las garantías realizadas con respecto al determinismo; ambos son útiles en diferentes circunstancias.
  - A menudo, las rutinas de API que transforman la aplicación de operaciones Quantum se pueden llevar a cabo de manera determinista y, por tanto, pueden estar disponibles como funciones como `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`.

- ✅ generalizar el tipo de entrada en la medida **de lo razonable** para cada función y operación, usando parámetros de tipo según sea necesario.

  *Ejemplos:*
  - `ApplyToEach` tiene el tipo `<'T>(('T => Unit), 'T[]) => Unit` en lugar del tipo específico de su aplicación más común, `((Qubit => Unit), Qubit[]) => Unit`.

> [!TIP]
> Es importante anticiparse a las necesidades futuras, pero también es importante solucionar problemas concretos de los usuarios.
> Actuando en este principio clave, por tanto, siempre requiere una consideración y un equilibrio cuidadosos para evitar el desarrollo de API "justo en caso".

**Principio clave:** elija los tipos de entrada y salida para las funciones y operaciones que son predecibles y que comunican el propósito de un objeto al que se puede llamar.

- ✅ **usar** tipos de tupla para agrupar lógicamente las entradas y salidas que solo son significativas cuando se consideran juntas. Considere la posibilidad de usar un tipo definido por el usuario en estos casos.

  *Ejemplos:*
  - Una función para generar los mínimos locales de otra función puede necesitar tomar límites de un intervalo de búsqueda como entrada, de modo que `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` puede ser una firma adecuada.
  - Una operación para calcular un derivado de un clasificador de aprendizaje automático mediante la técnica de cambio de parámetro puede necesitar tomar los vectores de parámetro desplazados y desplazados como entradas. En este caso, puede ser adecuada una entrada similar a `(unshifted : Double[], shifted : Double[])`.

- ✅ **realizar** el orden de los elementos en tuplas de entrada y salida de forma coherente en las distintas funciones y operaciones.

  *Ejemplos:*
  - Si tiene en cuenta dos funciones o u operaciones que toman un ángulo de giro y un qubit de destino como entradas, asegúrese de que se ordenan igual en cada tupla de entrada. Es decir, es preferible `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` y `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` y `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`.

**Principio clave:** diseñe funciones y operaciones para que funcionen bien con las características del lenguaje Q\# como la aplicación parcial.

- ✅ **realizan** el orden de los elementos en tuplas de entrada, de modo que las entradas que se aplican con más frecuencia se producen primero (es decir, para que la aplicación parcial actúe de forma similar a currificación).

  *Ejemplos:*
  - Una operación `ApplyRotation` que toma un número de punto flotante y un qubit como entradas se pueden aplicar a menudo parcialmente con la entrada de punto flotante para su uso con operaciones que esperan una entrada de tipo `Qubit => Unit`. Por lo tanto, una firma de `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      funcionaría de forma más coherente con la aplicación parcial.
  - Normalmente, esta guía implica la colocación de todos los datos clásicos antes de todos los qubits en tuplas de entrada, pero usa una buena resolución y examina cómo se llama a la API en la práctica.

## <a name="user-defined-types"></a>Tipos definidos por el usuario

**Principio clave:** use tipos definidos por el usuario para ayudar a que las API sean más expresivos y prácticas de usar.

- ✅ **introducir** nuevos tipos definidos por el usuario para proporcionar una abreviatura útil para tipos grandes o complicados.

  *Ejemplos:*
  - En los casos en los que un tipo de operación con tres entradas de matriz de qubit se suele tomar como entrada o se devuelve como salida, se proporciona un UDT como `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      puede ayudar a proporcionar una rápida utilidad.

- ✅ **introducir** nuevos tipos definidos por el usuario para indicar que un tipo base determinado solo debe usarse en un sentido muy determinado.

  *Ejemplos:*
  - Una operación que debe interpretarse específicamente como una operación que codifica datos clásico en un registro de Quantum puede ser adecuada para etiquetar con un tipo definido por el usuario `newtype InputEncoder = (Apply : (Qubit[] => Unit))`.

- ✅ **introducir** nuevos tipos definidos por el usuario con elementos con nombre que permitan la extensibilidad futura (por ejemplo: una estructura de resultados que pueda contener elementos con nombre adicionales en el futuro).

  *Ejemplos:*
  - Cuando una operación `TrainModel` expone un gran número de opciones de configuración, exponer estas opciones como un nuevo `TrainingOptions` UDT y proporcionar una nueva función `DefaultTrainingOptions : Unit -> TrainingOptions` permite a los usuarios invalidar elementos con nombre específicos en los valores de UDT de TrainingOptions y, al mismo tiempo, permitir que los desarrolladores de bibliotecas agreguen nuevos elementos UDT según corresponda.

- ✅ **DO** declare los elementos con nombre para los nuevos tipos definidos por el usuario en preferencia a fin de requerir a los usuarios que sepan la desconstrucción correcta de la tupla.

  *Ejemplos:*
  - Al representar un número complejo en su descomposición polar, prefiere `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` a `newtype ComplexPolar = (Double, Double)`.

**Principio clave:** use tipos definidos por el usuario de maneras que reduzcan la carga cognitiva y que no requieran que el usuario Aprenda conceptos y terminología adicionales.

- ⛔️ **no** presentan tipos definidos por el usuario que requieren que el usuario haga uso frecuente del operador Unwrap (`!`) o que normalmente requiere varios niveles de desencapsulado. Las posibles estrategias de mitigación incluyen:

  - Al exponer un tipo definido por el usuario con un solo elemento, considere la posibilidad de definir un nombre para ese elemento. Por ejemplo, considere la posibilidad de `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` en preferencia a `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`.

  - Asegurarse de que otras funciones y operaciones pueden aceptar directamente instancias de UDT "encapsuladas".

- ⛔️ **no** introducen nuevos tipos definidos por el usuario que dupliquen tipos integrados sin proporcionar expresividad adicional.

  *Ejemplos:*
  - Una `newtype QubitRegister = Qubit[]` UDT no proporciona ninguna expresividad adicional sobre `Qubit[]`y, por tanto, es más difícil de usar sin ninguna ventaja perceptible.
  - Un UDT `newtype LittleEndian = Qubit[]` documenta cómo se va a utilizar e interpretar el registro subyacente y, por tanto, proporciona expresividad adicional sobre su tipo base.

- ⛔️ **no** introducir funciones de descriptor de acceso a menos que sea estrictamente necesario;   es preferible utilizar elementos con nombre en este caso.

  *Ejemplos:*
  - Al introducir un UDT `newtype Complex = (Double, Double)`, es preferible modificar la definición para `newtype Complex = (Real : Double, Imag : Double)` a la presentación de funciones `GetReal : Complex -> Double` y `GetImag : Complex -> Double`.

## <a name="namespaces-and-organization"></a>Espacios de nombres y organización

**Principio clave:** elija los nombres de los espacios de nombres que sean predecibles y que comuniquen claramente el propósito de las funciones, operaciones y tipos definidos por el usuario en cada espacio de nombres.

- ✅ **asignar nombres a** los espacios de nombres como `Publisher.Product.DomainArea`.

  *Ejemplos:*
  - Las funciones, las operaciones y los UDT publicados por Microsoft como parte de la característica de simulación de Quantum del kit de desarrollo de Quantum se colocan en el espacio de nombres `Microsoft.Quantum.Simulation`.
  - `Microsoft.Quantum.Math` representa un espacio de nombres publicado por Microsoft como parte del kit de desarrollo de Quantum relacionado con el área de dominio de matemáticas.

- ✅ **realizar** operaciones, funciones y tipos definidos por el usuario que se usan para la funcionalidad específica en un espacio de nombres que describe esa funcionalidad, incluso cuando esa funcionalidad se usa en diferentes dominios de problemas.

  *Ejemplos:*
  - Las API de preparación de estado publicadas por Microsoft como parte del kit de desarrollo de Quantum se colocarían en `Microsoft.Quantum.Preparation`.
  - Las API de simulación de Quantum publicadas por Microsoft como parte del kit de desarrollo de Quantum se colocarían en `Microsoft.Quantum.Simulation`.

- ✅ **realizar** operaciones, funciones y tipos definidos por el usuario que solo se usen dentro de dominios específicos en espacios de nombres que indiquen su dominio de utilidad. Si es necesario, utilice subespacios de nombres para indicar las tareas enfocadas dentro de cada espacio de nombres específico del dominio.

  *Ejemplos:*
  - La biblioteca de aprendizaje automático de Quantum publicada por Microsoft se coloca en gran medida en el espacio de nombres @"microsoft.quantum.machinelearning", pero el espacio de nombres de ejemplo proporciona los conjuntos de valores de @"microsoft.quantum.machinelearning.datasets".
  - Las API de química de Quantum publicadas por Microsoft como parte del kit de desarrollo de Quantum deben colocarse en `Microsoft.Quantum.Chemistry`. La funcionalidad específica de la implementación de la descomposición de Jordania--Wigner se puede colocar en `Microsoft.Quantum.Chemistry.JordanWigner`, de modo que la interfaz principal para el área de dominio de química de Quantum no esté relacionada con las implementaciones.

**Principio clave:** Use espacios de nombres y modificadores de acceso juntos para ser intencionados sobre la superficie de API expuesta a los usuarios y para ocultar los detalles internos relacionados con la implementación y pruebas de las API.

- ✅ siempre que sea **razonable, coloque** todas las funciones y operaciones necesarias para implementar una API en el mismo espacio de nombres que la API que se implementa, pero con las palabras clave "Private" o "Internal" para indicar que no forman parte de la superficie de la API pública de una biblioteca. Use un nombre que comience por un carácter de subrayado (`_`) para distinguir visualmente las operaciones y funciones privadas e internas de las llamadas públicas.

  *Ejemplos:*
  - El nombre de la operación `_Features` indica una función que es privada para un espacio de nombres y ensamblado determinados y debe ir acompañada de la palabra clave `internal`.

- ✅ en el caso excepcional de que se necesite un amplio conjunto de funciones privadas u operaciones para implementar la API de un **espacio de nombres determinado,** colóquelas en un nuevo espacio de nombres que coincida con el espacio de nombres que se implementa y termine en `.Private`.

- ✅ **Coloque** todas las pruebas unitarias en espacios de nombres que coincidan con el espacio de nombres en pruebas y terminen en `.Tests`.

## <a name="naming-conventions-and-vocabulary"></a>Convenciones de nomenclatura y vocabulario

**Principio clave:** Elija nombres y terminología que sean claros, accesibles y legibles en una amplia variedad de audiencias, incluidos los expertos y usuarios de Quantum.

- ⛔️ **no** use nombres de identificador discriminatorios o de exclusión, ni terminología en los comentarios de documentación de la API.

- ✅ **usar** comentarios de documentación de API para proporcionar contexto, ejemplos y referencias relevantes, especialmente para conceptos más difíciles.

- ⛔️ **no** use nombres de identificador que sean innecesariamente esotéricos o que requieran conocimientos significativos de algoritmos Quantum para leer.

  *Ejemplos:*
  - Prefiere "iteración de amplificación de amplitud" a "iteración de Grover".

- ✅ **Elija** las operaciones y los nombres de función que comuniquen claramente el efecto previsto de una operación invocable y no su implementación. Tenga en cuenta que la implementación puede y debe ser

  *Ejemplos:*
  - Prefiere "estimar superposición" a "prueba de Hadamard", ya que la última comunica cómo se implementa la primera.

- ✅ **usar** palabras de manera coherente en todas las api Q\#:

  - **Verbos**

    - **Assert**: Compruebe que una suposición sobre el estado de un equipo de destino y su qubits contiene, posiblemente mediante recursos no físicos. Las operaciones que utilizan este verbo siempre deben ser extraíbles de forma segura sin que ello afecte a la funcionalidad de las bibliotecas y programas ejecutables. Tenga en cuenta que, a diferencia de los hechos, las aserciones pueden en general depender del estado externo, como el estado de un registro qubit, el entorno de ejecución, etc. Dado que la dependencia del estado externo es un tipo de efecto secundario, las aserciones deben exponerse como operaciones en lugar de funciones.

    - **Estimación**: el uso de una o varias mediciones posiblemente repetidas calcula una cantidad clásica a partir de los resultados de la medición.

      *Ejemplos:*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Preparar**: Aplique una operación Quantum o una secuencia de operaciones a uno o varios qubits que se supone que se inician en un estado inicial determinado (normalmente $ \ket{00\cdots 0} $), lo que hace que el estado de esas qubits evolucione a un estado final deseado. En general, la actuación en Estados distintos del estado de inicio dado **puede** dar lugar a una transformación de unitario sin definir, pero **debe** conservar todavía una operación y su "cancelar salida" y aplicar una operación no operativa.

      *Ejemplos:*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Medida**: Aplique una operación Quantum o una secuencia de operaciones a uno o varios qubits, y vuelva a leer los datos de la clásica.

      *Ejemplos:*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Apply**: aplica una operación Quantum o una secuencia de operaciones a uno o varios qubits, lo que hace que el estado de esos qubitss cambie de manera coherente. Este verbo es el verbo más general en Q\# Nomenclature y **no debe** usarse cuando un verbo más específico es más relevante directamente.

  - **Nombres**:

    - **Hecho**: una condición booleana que depende solo de sus entradas y no del estado de una máquina de destino, su entorno o el estado de la qubits de la máquina. Al contrario que una aserción, un hecho solo es sensible a los *valores* proporcionados en ese hecho. Por ejemplo:

      *Ejemplos:*
      - @"microsoft.quantum.diagnostics.equalityfacti": representa un hecho de igualdad sobre dos entradas de enteros; los enteros que se proporcionan como entrada son iguales o no, independientemente de cualquier otro estado del programa.

    - **Opciones:** Un UDT que contiene varios elementos con nombre que pueden actuar como "argumentos opcionales" para una función u operación. Por ejemplo:

      *Ejemplos:*
      - El @"microsoft.quantum.machinelearning.trainingoptions" UDT incluye elementos con nombre para la velocidad de aprendizaje, el tamaño de minilote y otros parámetros configurables para aprendizaje de ML.

  - **Adjetivos**:

    - ⛔️ **New**: este adjetivo **no debe** usarse, como para evitar la confusión con su uso como verbo en muchos lenguajes de programación (por C++ejemplo C#:,, Java, TypeScript, PowerShell).

  - **Posiciones preposicionadas:** En algunos casos, se pueden usar las preposiciones para eliminar la ambigüedad o clarificar los roles de sustantivos y verbos en los nombres de función y de operación. Sin embargo, se debe tener cuidado de hacerlo de forma moderada y coherente.

    - **Como:** Representa que la entrada y la salida de una función representan la misma información, pero que la salida representa esa información **como** una *X* en lugar de su representación original. Esto es especialmente común para las funciones de conversión de tipos.

      *Ejemplos:*
      - `IntAsDouble(2)` indica que tanto la entrada (`2`) como la salida (`2.0`) representan cualitativamente la misma información, pero con diferentes tipos de datos Q\# para hacerlo.

    - **Desde:** Para garantizar la coherencia, esta preposición **no se debe** utilizar para indicar las funciones de conversión de tipos o cualquier otro **caso en el que sea adecuado** .

    - ⛔️ **a:** **no se debe** usar esta preposición, como para evitar la confusión con su uso como verbo en muchos lenguajes de programación.
