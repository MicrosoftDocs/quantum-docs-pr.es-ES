---
title: Carga de una función de Hamilton desde un archivo
description: Obtenga información acerca de cómo generar automáticamente un Hamiltonian grande con el esquema Broombridge.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
no-loc:
- Q#
- $$v
ms.openlocfilehash: 57e25bf55009797b01695cef0f3d29b94662ccc0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869246"
---
# <a name="loading-a-hamiltonian-from-file"></a>Carga de una función de Hamilton desde un archivo
Anteriormente, construimos Hamiltonians agregando términos individuales. Aunque esto es adecuado para pequeños ejemplos, la química de Quantum a escala requiere Hamiltonians con millones o miles de millones de términos. Tales Hamiltonians, generados por paquetes de química como NWChem, son demasiado grandes para importar a mano. En este ejemplo, se muestra cómo `FermionHamiltonian` se puede generar automáticamente una instancia a partir de una molécula representada por el [esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge). Como referencia, puede inspeccionar el `LithiumHydrideGUI` ejemplo proporcionado o el `RunSimulation` ejemplo. También hay compatibilidad limitada para importar desde el formato utilizado por [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).

Veamos el ejemplo de la molécula de nitrógeno, que se proporciona en la `IntegralData/YAML` carpeta del repositorio de ejemplos. El método para cargar el `Broombridge` esquema es sencillo.

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

El esquema Broombridge también contiene sugerencias para el estado inicial que se va a preparar. Las etiquetas, por ejemplo `"|G⟩"` `"|E1⟩"` , o, para estos Estados pueden verse mediante la inspección del archivo. Con el fin de preparar estos estados iniciales, el `qSharpData` consumido por los Q# algoritmos Quantum se obtiene de forma similar a la [sección anterior](xref:microsoft.quantum.chemistry.examples.energyestimate), pero con un parámetro adicional que selecciona el estado inicial deseado. Por ejemplo,
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

Todos los pasos anteriores se pueden abreviar con los métodos de conveniencia proporcionados, como se indica a continuación.
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

También se puede cargar un Hamiltonian desde el LIQUi |> formato, con una sintaxis muy similar. 

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

Al seguir este proceso desde cualquier instancia de Broombridge, o cualquier paso intermedio, se pueden ejecutar algoritmos Quantum como la estimación de la fase de Quantum en el problema de estructura electrónica especificado.
