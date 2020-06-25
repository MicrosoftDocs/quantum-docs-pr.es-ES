---
title: Contribución del código a Microsoft QDK
description: Obtenga información sobre cómo colaborar en el Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: edc52dc4434e91258bece28812fd76b66329c6f9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275485"
---
# <a name="contributing-code"></a><span data-ttu-id="03122-103">Contribución de código</span><span class="sxs-lookup"><span data-stu-id="03122-103">Contributing Code</span></span>

<span data-ttu-id="03122-104">Además de notificar problemas y mejorar la documentación, el código que contribuye al kit de desarrollo de Quantum puede ser una forma muy directa de ayudar a sus colegas en la comunidad de programación Quantum.</span><span class="sxs-lookup"><span data-stu-id="03122-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="03122-105">Al contribuir con el código, puede ayudar a solucionar problemas, proporcionar nuevos ejemplos, facilitar el uso de las bibliotecas existentes o incluso agregar características completamente nuevas.</span><span class="sxs-lookup"><span data-stu-id="03122-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="03122-106">En esta guía, detallaremos un poco de lo que se busca cuando revisemos las solicitudes de incorporación de cambios para ayudar a que su contribución sea lo más conveniente.</span><span class="sxs-lookup"><span data-stu-id="03122-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="03122-107">Qué buscamos</span><span class="sxs-lookup"><span data-stu-id="03122-107">What We Look For</span></span>

<span data-ttu-id="03122-108">Una contribución de código ideal se basa en el trabajo existente en un repositorio de Quantum Development Kit para corregir problemas, expandir características existentes o agregar nuevas características que se encuentran dentro del ámbito de un repositorio.</span><span class="sxs-lookup"><span data-stu-id="03122-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="03122-109">Cuando aceptamos una contribución del código, se convierte en parte del kit de desarrollo de Quantum, de modo que las nuevas características se publiquen, se mantendrán y se desarrollen de la misma manera que el resto del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="03122-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="03122-110">Por lo tanto, resulta útil cuando la funcionalidad agregada por una contribución está bien probada y está documentada.</span><span class="sxs-lookup"><span data-stu-id="03122-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="03122-111">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="03122-111">Unit Tests</span></span>

<span data-ttu-id="03122-112">Las funciones, operaciones y tipos definidos por el usuario de preguntas y respuestas que componen bibliotecas como la Canon se prueban automáticamente como parte del desarrollo en el repositorio [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .</span><span class="sxs-lookup"><span data-stu-id="03122-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="03122-113">Cuando se abre una nueva solicitud de incorporación de cambios, por ejemplo, la configuración de [Azure pipelines](https://azure.microsoft.com/services/devops/pipelines/) comprobará que los cambios en la solicitud de incorporación de cambios no interrumpan ninguna funcionalidad existente de la que dependa la comunidad de programación de Quantum.</span><span class="sxs-lookup"><span data-stu-id="03122-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="03122-114">Con la versión más reciente de Q #, la prueba unitaria se define mediante el `@Test("QuantumSimulator")` atributo.</span><span class="sxs-lookup"><span data-stu-id="03122-114">With the latest Q# version, unit test are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="03122-115">El argumento puede ser "QuantumSimulator", "ToffoliSimulator", "TraceSimulator" o cualquier nombre completo que especifique el destino de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="03122-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the execution target.</span></span> <span data-ttu-id="03122-116">Varios atributos que definen distintos destinos de ejecución se pueden adjuntar a la misma.</span><span class="sxs-lookup"><span data-stu-id="03122-116">Several attributes defining different execution targets may be attached to the same callable.</span></span> <span data-ttu-id="03122-117">Algunas de nuestras pruebas siguen usando el paquete [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) en desuso que expone todas las funciones y operaciones de Q # que terminan en `Test` el marco de [xUnit](https://xunit.github.io/) .</span><span class="sxs-lookup"><span data-stu-id="03122-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="03122-118">Este paquete ya no es necesario para definir pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="03122-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="03122-119">La siguiente función se usa para garantizar que las <xref:microsoft.quantum.canon.fst> <xref:microsoft.quantum.canon.snd> funciones y devuelven los resultados correctos en un ejemplo representativo.</span><span class="sxs-lookup"><span data-stu-id="03122-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="03122-120">Si la salida de `Fst` o `Snd` es incorrecta, la `fail` instrucción se utiliza para hacer que la prueba genere un error.</span><span class="sxs-lookup"><span data-stu-id="03122-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="03122-121">Se pueden comprobar condiciones más complicadas mediante las técnicas de la [sección pruebas](xref:microsoft.quantum.libraries.diagnostics) de la guía de bibliotecas estándar.</span><span class="sxs-lookup"><span data-stu-id="03122-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="03122-122">Por ejemplo, las siguientes comprobaciones de prueba que `H(q); X(q); H(q);` , como llama, <xref:microsoft.quantum.canon.applywith> hace lo mismo que `Z(q)` .</span><span class="sxs-lookup"><span data-stu-id="03122-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="03122-123">Al agregar nuevas características, se recomienda agregar también nuevas pruebas para asegurarse de que la contribución realiza lo que se supone.</span><span class="sxs-lookup"><span data-stu-id="03122-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="03122-124">Esto ayuda al resto de la comunidad a mantener y desarrollar su característica y, en particular, ayuda a otros desarrolladores a saber que pueden confiar en su característica.</span><span class="sxs-lookup"><span data-stu-id="03122-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="03122-125">Esto también funciona de la otra manera.</span><span class="sxs-lookup"><span data-stu-id="03122-125">This works the other way around, too!</span></span>
> <span data-ttu-id="03122-126">Si hay una característica existente que no tiene algunas pruebas, ayudarnos a agregar cobertura de pruebas supondrá una gran contribución a la comunidad.</span><span class="sxs-lookup"><span data-stu-id="03122-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="03122-127">Localmente, las pruebas unitarias se pueden ejecutar mediante el explorador de pruebas de Visual Studio o el `dotnet test` comando, para que pueda comprobar su contribución antes de abrir una solicitud de incorporación de cambios.</span><span class="sxs-lookup"><span data-stu-id="03122-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="03122-128">Cuándo se rechazará una solicitud de incorporación de cambios</span><span class="sxs-lookup"><span data-stu-id="03122-128">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="03122-129">A veces, rechazaremos la solicitud de incorporación de cambios para una contribución.</span><span class="sxs-lookup"><span data-stu-id="03122-129">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="03122-130">Si esto sucede, no significa que sea malo, ya que hay una serie de motivos por los que es posible que no podamos aceptar una contribución determinada.</span><span class="sxs-lookup"><span data-stu-id="03122-130">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="03122-131">Quizás lo más habitual es que una contribución a la comunidad de programación Quantum sea realmente buena, pero los repositorios del kit de desarrollo Quantum no son el lugar adecuado para desarrollarla.</span><span class="sxs-lookup"><span data-stu-id="03122-131">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="03122-132">En tales casos, le recomendamos encarecidamente que cree su propio repositorio---parte de la fuerza del kit de desarrollo de Quantum es que es fácil crear y distribuir sus propias bibliotecas con GitHub y NuGet.org, de la misma manera que se distribuyen las bibliotecas de Canon y química hoy en día.</span><span class="sxs-lookup"><span data-stu-id="03122-132">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="03122-133">En otras ocasiones, podemos rechazar una buena contribución simplemente porque todavía no estamos preparados para mantenerla y desarrollarla.</span><span class="sxs-lookup"><span data-stu-id="03122-133">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="03122-134">Puede ser difícil hacer todo, por lo que planeamos en qué características es mejor trabajar como guía.</span><span class="sxs-lookup"><span data-stu-id="03122-134">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="03122-135">Puede ser otro caso en el que la liberación de una característica como biblioteca de terceros puede tener mucho sentido.</span><span class="sxs-lookup"><span data-stu-id="03122-135">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="03122-136">Como alternativa, es posible que le pidamos su ayuda en la modificación de una característica para ajustarse mejor a nuestra guía básica, de modo que podamos hacer el mejor trabajo que podamos con ella.</span><span class="sxs-lookup"><span data-stu-id="03122-136">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="03122-137">También se pedirán cambios en una solicitud de incorporación de cambios si se requiere más documentación o pruebas unitarias para ayudarnos a usarlas, o si difiere bastante en el estilo del resto de las bibliotecas de Q #, de forma que sea más difícil para los usuarios encontrar la característica.</span><span class="sxs-lookup"><span data-stu-id="03122-137">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="03122-138">En estos casos, intentaremos ofrecer algunos consejos en las revisiones de código sobre lo que se puede Agregar o cambiar para que podamos incluir su contribución.</span><span class="sxs-lookup"><span data-stu-id="03122-138">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="03122-139">Por último, no podemos aceptar contribuciones que causan el daño de la comunidad Quantum Computing, como se describe en el [código de conducta de código abierto de Microsoft](https://opensource.microsoft.com/codeofconduct/).</span><span class="sxs-lookup"><span data-stu-id="03122-139">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="03122-140">Queremos asegurarnos de que las contribuciones sirvan a toda la comunidad Quantum Computing, tanto en su actual diversidad actual como en el futuro, a medida que crezcan aún más.</span><span class="sxs-lookup"><span data-stu-id="03122-140">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="03122-141">Agradecemos su ayuda para alcanzar este objetivo.</span><span class="sxs-lookup"><span data-stu-id="03122-141">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="03122-142">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="03122-142">Next steps</span></span>

<span data-ttu-id="03122-143">Gracias por ayudarnos a que el kit de desarrollo de Quantum sea un excelente recurso para toda la comunidad de programación de Quantum.</span><span class="sxs-lookup"><span data-stu-id="03122-143">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="03122-144">Para obtener más información, continúe con la siguiente guía sobre el estilo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="03122-144">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="03122-145">Más información sobre las directrices de estilo de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="03122-145">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="03122-146">En función del tipo de código que esté contribuyendo, es posible que tenga que tener en cuenta aspectos adicionales que pueden ayudarle a hacer que su contribución sea lo más conveniente para la comunidad como sea posible.</span><span class="sxs-lookup"><span data-stu-id="03122-146">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="03122-147">Más información sobre los ejemplos de contribución</span><span class="sxs-lookup"><span data-stu-id="03122-147">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
