---
title: 'Variables locales: técnicas de Q # | Microsoft Docs'
description: 'Variables locales: técnicas de preguntas y respuestas'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: 8b1de5c096210fb36a81c127a8bbbe1b39522741
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820188"
---
# <a name="local-variables"></a><span data-ttu-id="9cf5a-103">Variables locales</span><span class="sxs-lookup"><span data-stu-id="9cf5a-103">Local Variables</span></span> #

<span data-ttu-id="9cf5a-104">Un valor de cualquier tipo en Q # se puede asignar a una variable para su reutilización en una operación o función mediante la palabra clave `let`.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="9cf5a-105">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9cf5a-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="9cf5a-106">Esto asigna una matriz determinada de operadores Pauli a una variable denominada `measurementOperator`.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="9cf5a-107">Tenga en cuenta que no es necesario especificar explícitamente el tipo de la nueva variable, ya que la expresión del lado derecho de la instrucción `let` es inequívoca y el compilador deduce el tipo.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="9cf5a-108">Las variables de Q # son *inmutables*, lo que significa que una vez que una variable se ha definido de esta manera, ya no se puede cambiar de ningún modo.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="9cf5a-109">Esto permite varias optimizaciones beneficiosas, incluida la optimización de la lógica clásica que actúa en las variables que se van a reordenar para aplicar el `Adjoint` variante de una operación.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="9cf5a-110">Las variables definidas mediante el enlace de `let` como se indica a continuación son locales para un ámbito determinado, como el cuerpo de una operación o el contenido de un bucle de `for`.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="9cf5a-111">Mutabilidad</span><span class="sxs-lookup"><span data-stu-id="9cf5a-111">Mutability</span></span> ##

<span data-ttu-id="9cf5a-112">Como alternativa a la creación de una variable con `let`, la palabra clave `mutable` creará una variable mutable especial que se puede volver a enlazar después de que se haya creado inicialmente mediante la palabra clave `set`.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="9cf5a-113">Todos los tipos de Q #, incluidas las matrices, siguen la semántica de valor.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="9cf5a-114">En concreto, no es posible actualizar los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="9cf5a-115">Para modificar una matriz existente, es necesario aprovechar un mecanismo de copia y actualización como el de los registros de F#.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="9cf5a-116">Mediante el uso de las herramientas de biblioteca para las matrices que se proporcionan en [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), podemos, por ejemplo, definir fácilmente una función que devuelve una matriz de Paulis donde Pauli en el índice `i` toma el valor especificado y todas las demás entradas son la identidad:</span><span class="sxs-lookup"><span data-stu-id="9cf5a-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="9cf5a-117">Veremos más sobre cómo trabajar con matrices al hablar de instrucciones y expresiones de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="9cf5a-118">La mutabilidad en Q # es un concepto que se aplica a un *símbolo* en lugar de un tipo o valor.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="9cf5a-119">En concreto, no tiene una representación en el sistema de tipos, implícita o explícitamente, y si un enlace es mutable (según lo indicado por la palabra clave `mutable`) o inmutable (como se indica en `let`) no cambia el tipo de las variables enlazadas.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="9cf5a-120">Esto proporciona una manera importante de aislar la mutabilidad dentro de funciones y operaciones especializadas.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="9cf5a-121">En concreto, aunque no se puede generar automáticamente una especialización de un método contiguo para una operación que utiliza una variable mutable, la generación automática funciona correctamente para una operación que llama a una función que utiliza mutabilidad.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="9cf5a-122">Por esta razón, se recomienda hacer que las funciones y operaciones usen mutabilidad como cortas y compactas como sea posible, para que el resto del programa Quantum pueda escribirse mediante variables immutables ordinarias.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="9cf5a-123">Deconstrucción</span><span class="sxs-lookup"><span data-stu-id="9cf5a-123">Deconstruction</span></span> ##

<span data-ttu-id="9cf5a-124">Además de asignar una sola variable, las palabras clave `let` y `mutable` (o de hecho cualquier otra construcción de enlace) también permiten desempaquetar el contenido de un [tipo de tupla](xref:microsoft.quantum.language.type-model#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="9cf5a-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="9cf5a-125">Se dice que una asignación de este formulario *deconstruye* los elementos de esa tupla.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="9cf5a-126">Por ejemplo, si modelamos un término en un Hamiltonian por una tupla, podemos usar la desconstrucción para tener acceso a los datos diferentes que necesitamos simular en ese plazo:</span><span class="sxs-lookup"><span data-stu-id="9cf5a-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


