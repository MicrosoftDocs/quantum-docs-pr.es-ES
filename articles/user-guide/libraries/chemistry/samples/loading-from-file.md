---
title: Carga de una función de Hamilton desde un archivo
description: Obtenga información acerca de cómo generar automáticamente un Hamiltonian grande con el esquema Broombridge.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 715dbcefc10ecc5af45f2bdd228890f1cb28886b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275245"
---
# <a name="loading-a-hamiltonian-from-file"></a><span data-ttu-id="5ecd5-103">Carga de una función de Hamilton desde un archivo</span><span class="sxs-lookup"><span data-stu-id="5ecd5-103">Loading a Hamiltonian from file</span></span>
<span data-ttu-id="5ecd5-104">Anteriormente, construimos Hamiltonians agregando términos individuales.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-104">Previously, we constructed Hamiltonians by adding individual terms to it.</span></span> <span data-ttu-id="5ecd5-105">Aunque esto es adecuado para pequeños ejemplos, la química de Quantum a escala requiere Hamiltonians con millones o miles de millones de términos.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-105">While this is fine for small examples, quantum chemistry at scale require Hamiltonians with millions or billions of terms.</span></span> <span data-ttu-id="5ecd5-106">Tales Hamiltonians, generados por paquetes de química como NWChem, son demasiado grandes para importar a mano.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-106">Such Hamiltonians, generated by chemistry packages such as NWChem, are too large to import by hand.</span></span> <span data-ttu-id="5ecd5-107">En este ejemplo, se muestra cómo `FermionHamiltonian` se puede generar automáticamente una instancia a partir de una molécula representada por el [esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="5ecd5-107">In this sample, we illustrate how a `FermionHamiltonian` instance may be automatically generated from a molecule represented by the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span> <span data-ttu-id="5ecd5-108">Como referencia, puede inspeccionar el `LithiumHydrideGUI` ejemplo proporcionado o el `RunSimulation` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-108">For reference, one may inspect the provided `LithiumHydrideGUI` sample, or the `RunSimulation` sample.</span></span> <span data-ttu-id="5ecd5-109">También hay compatibilidad limitada para importar desde el formato utilizado por [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).</span><span class="sxs-lookup"><span data-stu-id="5ecd5-109">Limited support is also available for importing from the format consumed by [LIQUi|>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).</span></span>

<span data-ttu-id="5ecd5-110">Veamos el ejemplo de la molécula de nitrógeno, que se proporciona en la `IntegralData/YAML` carpeta del repositorio de ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-110">Let us consider the example of the Nitrogen molecule, which is provided in the `IntegralData/YAML` folder of the samples repository.</span></span> <span data-ttu-id="5ecd5-111">El método para cargar el `Broombridge` esquema es sencillo.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-111">The method for loading the `Broombridge` schema is straightforward.</span></span>

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

<span data-ttu-id="5ecd5-112">El esquema Broombridge también contiene sugerencias para el estado inicial que se va a preparar.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-112">The Broombridge schema also contains suggestions for the initial state to be prepared.</span></span> <span data-ttu-id="5ecd5-113">Las etiquetas, por ejemplo `"|G⟩"` `"|E1⟩"` , o, para estos Estados pueden verse mediante la inspección del archivo.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-113">The labels, e.g. `"|G⟩"` or `"|E1⟩"`, for these states may be seen by inspecting the file.</span></span> <span data-ttu-id="5ecd5-114">Con el fin de preparar estos estados iniciales, el `qSharpData` consumido por los algoritmos Q # Quantum se obtiene de forma similar a la [sección anterior](xref:microsoft.quantum.chemistry.examples.energyestimate), pero con un parámetro adicional que selecciona el estado inicial deseado.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-114">In order to prepare these initial states, the `qSharpData` consumed by the Q# quantum algorithms is obtained similar to the [previous section](xref:microsoft.quantum.chemistry.examples.energyestimate), but with an additional parameter selecting the desired initial state.</span></span> <span data-ttu-id="5ecd5-115">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="5ecd5-115">For instance,</span></span>
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="5ecd5-116">Todos los pasos anteriores se pueden abreviar con los métodos de conveniencia proporcionados, como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-116">All the above steps may be abbreviated using provided convenience methods as follows.</span></span>
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

<span data-ttu-id="5ecd5-117">También se puede cargar un Hamiltonian desde el LIQUi |> formato, con una sintaxis muy similar.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-117">We may also load a Hamiltonian from the LIQUi|> format, using a very similar syntax.</span></span> 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="5ecd5-118">Al seguir este proceso desde cualquier instancia de Broombridge, o cualquier paso intermedio, se pueden ejecutar algoritmos Quantum como la estimación de la fase de Quantum en el problema de estructura electrónica especificado.</span><span class="sxs-lookup"><span data-stu-id="5ecd5-118">By following this process from any instance of Broombridge, or any intermediate step, quantum algorithms such as quantum phase estimation may be run on the specified electronic structure problem.</span></span>