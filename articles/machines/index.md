---
title: Simuladores cuánticos y aplicaciones host | Microsoft Docs
description: Describe cómo impulsar los simuladores cuánticos con un lenguaje informático clásico .NET, por lo general C# o Q#.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 14aed75ed0ed192f88699b1c7dbacfae23f74642
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442222"
---
# <a name="quantum-simulators-and-host-applications"></a>Simuladores cuánticos y aplicaciones host

## <a name="what-youll-learn"></a>Temas que se abordarán

> [!div class="checklist"]
> * Ejecución de algoritmos cuánticos
> * Simuladores cuánticos incluidos en esta versión
> * Escritura de un controlador C# para un algoritmo cuántico

## <a name="the-quantum-development-kit-execution-model"></a>El modelo de ejecución de Quantum Development Kit

En [Escritura de un programa cuántico](xref:microsoft.quantum.write-program), ejecutamos el algoritmo cuántico al pasar un objeto `QuantumSimulator` al método `Run` de la clase del algoritmo.
La clase `QuantumSimulator` ejecuta el algoritmo cuántico mediante la simulación completa del vector de estado cuántico, que es ideal para ejecutar y probar `Teleport`.
Consulte la [Guía de conceptos](xref:microsoft.quantum.concepts.intro) para más información sobre los vectores de estados cuánticos.

Se pueden usar otras máquinas de destino para ejecutar un algoritmo cuántico.
La máquina es responsable de proporcionar las implementaciones de primitivas cuánticas del algoritmo.
Esto incluye operaciones primitivas como H, CNOT y Measure, así como el seguimiento y la administración de cúbits.
Las distintas clases de máquinas cuánticas representan modelos de ejecución diferentes para el mismo algoritmo cuántico.

Cada tipo de máquina cuántica puede ofrecer distintas implementaciones de estas operaciones primitivas.
Por ejemplo, el simulador de seguimiento de equipos cuánticos incluido en el kit de desarrollo no realiza ninguna simulación en lo absoluto.
En su lugar, hace un seguimiento del uso de puertas, cúbits y otros recursos para el algoritmo.

### <a name="quantum-machines"></a>Máquinas cuánticas

En el futuro, se definirán clases de máquinas cuánticas adicionales para admitir otros tipos de simulación y la ejecución en equipos cuánticos topológicos.
Permitir que el algoritmo permanezca constante mientras varía la implementación de la máquina subyacente permite facilitar la prueba y depuración de un algoritmo en la simulación y, después, ejecutarlo en hardware real con la confianza de que el algoritmo no haya cambiado.

### <a name="whats-included-in-this-release"></a>Lo que incluye esta versión

Esta versión de Quantum Developer Kit incluye varias clases de máquinas cuánticas.
Todas ellas se definen en el espacio de nombres `Microsoft.Quantum.Simulation.Simulators`.

* Un [simulador de vector de estado completo](xref:microsoft.quantum.machines.full-state-simulator), la clase `QuantumSimulator`.
* Un [estimador de recursos sencillo](xref:microsoft.quantum.machines.resources-estimator), la clase `ResourcesEstimator`, permite un análisis de nivel superior de los recursos necesarios para ejecutar un algoritmo cuántico.
* Un [estimador de recursos basado en seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro), la clase `QCTraceSimulator`, permite un análisis de nivel superior de los recursos necesarios para ejecutar un algoritmo cuántico.
* Un [simulador de Toffoli](xref:microsoft.quantum.machines.toffoli-simulator), la clase `ToffoliSimulator`.

## <a name="writing-a-host-application"></a>Escritura de una aplicación host

En [Escritura de un programa cuántico](xref:microsoft.quantum.write-program), escribimos un controlador C# sencillo para el algoritmo de teletransporte. Un controlador C# tiene 4 propósitos principales:

* Construir la máquina de destino
* Calcular los argumentos necesarios para el algoritmo cuántico
* Ejecutar el algoritmo cuántico mediante el simulador
* Procesar el resultado de la operación

Aquí analizaremos cada paso con más detalle.

### <a name="constructing-the-target-machine"></a>Construcción de la máquina de destino

Las máquinas cuánticas son instancias de las clases .NET normales, por lo que se crean mediante la invocación de su constructor, del mismo modo que cualquier clase .NET.
Algunos simuladores, incluido `QuantumSimulator`, implementan la interfaz <xref:System.IDisposable?displayProperty=nameWithType> de .NET, por lo que se deben encapsular en una instrucción `using` de C#.

### <a name="computing-arguments-for-the-algorithm"></a>Cálculo de argumentos para el algoritmo

En el ejemplo de `Teleport`, calculamos algunos argumentos relativamente artificiales para pasar al algoritmo cuántico.
Sin embargo, por lo general, el algoritmo cuántico requiere muchos datos y es fácil proporcionarlos desde el controlador clásico.

Por ejemplo, al realizar simulaciones químicas, el algoritmo cuántico requiere una tabla grande de integrales de interacción orbital molecular.
Por lo general, se leen desde un archivo que se proporciona al ejecutar el algoritmo.
Como Q# no tiene un mecanismo para acceder al sistema de archivos, este tipo de datos lo recopila de mejor manera el controlador clásico y, luego, se pasa al método `Run` del algoritmo cuántico.

Otro caso en el que el controlador clásico desempeña un papel clave es en los métodos variacionales.
En esta clase de algoritmos, un estado cuántico se prepara en función de algunos parámetros clásicos y ese estado se usa para calcular algún valor de interés.
Los parámetros se ajustan en función de algún tipo de algoritmo de aprendizaje automático o de escalada y el algoritmo cuántico se vuelve a ejecutar.
En estos algoritmos, el algoritmo de escalada en sí se implementa mejor como una función puramente clásica a la que llama el controlador clásico; los resultados del algoritmo de escalada entonces se pasa a la ejecución siguiente del algoritmo cuántico.

### <a name="running-the-quantum-algorithm"></a>Ejecución del algoritmo cuántico

Esta parte suele ser muy sencilla.
Cada operación de Q # se compila en una clase que proporciona un método `Run` estático.
Los argumentos para este método los proporciona la tupla plana de argumento de la operación misma, además de un primer argumento adicional, que es el simulador con el cual se realiza la ejecución. Para una operación que espera la tupla denominada de tipo `(a: String, (b: Double, c: Double))`, su contraparte plana es de tipo `(String a, Double b, Double c)`.


Existen algunos matices al pasar argumentos a un método `Run`:

* Las matrices se deben encapsular en un objeto `Microsoft.Quantum.Simulation.Core.QArray<T>`.
    Una clase `QArray` tiene un constructor que puede tomar cualquier colección ordenada (`IEnumerable<T>`) de los objetos adecuados.
* La tupla vacía, `()` en Q#, se representa con `QVoid.Instance` en C#.
* Las tuplas no vacías se representan como instancias `ValueTuple` de .NET.
* Los tipos de Q# definidos por el usuario se pasan como su tipo base.
* Para pasar una operación o función a un método `Run`, debe obtener una instancia de la clase de la operación o una clase de la función, a través del método `Get<>` del simulador.

### <a name="processing-the-results"></a>Procesamiento de los resultados

Los resultados del algoritmo cuántico se devuelven desde el método `Run`.
El método `Run` se ejecuta de manera asincrónica, por lo que devuelva una instancia de <xref:System.Threading.Tasks.Task`1>.
Hay varias maneras de obtener los resultados reales de la operación. La más simple es mediante la propiedad [`Result` de`Task`](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
pero otras técnicas, como usar el [`Wait` método](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) o la [`await` palabra clave](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) de C# también funcionarán.

Al igual que con los argumentos, las tuplas de Q# se representan como instancias `ValueTuple` y las matrices de Q#, como instancias `QArray`.
Los tipos definidos por el usuario se devuelven como sus tipo bases.
La tupla vacía, `()`, se devuelve como una instancia de la clase `QVoid`.

Muchos algoritmos cuánticos requieren un procesamiento posterior sustancial para derivar respuestas útiles.
Por ejemplo, la parte cuántica del algoritmo de Shor es solo el comienzo de un cálculo que busca los factores de un número.

En la mayoría de los casos, es más sencillo y más fácil realizar este tipo de procesamiento posterior en el controlador clásico.
Solo el controlador clásico puede informar de los resultados al usuario o escribirlos en el disco.
El controlador clásico tendrá acceso a las bibliotecas de análisis y a otras funciones matemáticas que no se exponen en Q#.


## <a name="failures"></a>Errores

Cuando la instrucción `fail` de Q# se alcanza durante la ejecución de una operación, se genera una excepción `ExecutionFailException`.

Debido al uso de `System.Task` en el método `Run`, la excepción que se genera como resultado de una instrucción `fail` se encapsulará en una excepción `System.AggregateException`.
Para encontrar la razón real del error, debe iterar en `AggregateException` 
`InnerExceptions`, por ejemplo:

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a>Otros lenguajes clásicos

Aunque los ejemplos que proporcionamos se encuentran en C#, F# y Python, Quantum Development Kit también admite la escritura de programas host clásicos en otros lenguajes.
Por ejemplo, si quiere escribir un programa host en Visual Basic, [debería funcionar correctamente](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).
