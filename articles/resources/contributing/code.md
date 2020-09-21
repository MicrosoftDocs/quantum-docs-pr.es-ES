---
title: Contribución del código a Microsoft QDK
description: Obtenga información sobre cómo colaborar en el Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: b27d084bbe2cda878efa6250c52c0ae628637850
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834897"
---
# <a name="contributing-code"></a>Contribución de código

Además de notificar problemas y mejorar la documentación, el código que contribuye al kit de desarrollo de Quantum puede ser una forma muy directa de ayudar a sus colegas en la comunidad de programación Quantum.
Al contribuir con el código, puede ayudar a solucionar problemas, proporcionar nuevos ejemplos, facilitar el uso de las bibliotecas existentes o incluso agregar características completamente nuevas.

En esta guía, detallaremos un poco de lo que se busca cuando revisemos las solicitudes de incorporación de cambios para ayudar a que su contribución sea lo más conveniente.

## <a name="what-we-look-for"></a>Qué buscamos

Una contribución de código ideal se basa en el trabajo existente en un repositorio de Quantum Development Kit para corregir problemas, expandir características existentes o agregar nuevas características que se encuentran dentro del ámbito de un repositorio.
Cuando aceptamos una contribución del código, se convierte en parte del kit de desarrollo de Quantum, de modo que las nuevas características se publiquen, se mantendrán y se desarrollen de la misma manera que el resto del kit de desarrollo de Quantum.
Por lo tanto, resulta útil cuando la funcionalidad agregada por una contribución está bien probada y está documentada.

### <a name="unit-tests"></a>Pruebas unitarias

Las Q# funciones, operaciones y tipos definidos por el usuario que componen bibliotecas como la Canon se prueban automáticamente como parte del desarrollo en el repositorio [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) .
Cuando se abre una nueva solicitud de incorporación de cambios, por ejemplo, la configuración de [Azure pipelines](https://azure.microsoft.com/services/devops/pipelines/) comprobará que los cambios en la solicitud de incorporación de cambios no interrumpan ninguna funcionalidad existente de la que dependa la comunidad de programación de Quantum.

Con la versión más reciente Q# , las pruebas unitarias se definen mediante el `@Test("QuantumSimulator")` atributo. El argumento puede ser "QuantumSimulator", "ToffoliSimulator", "TraceSimulator" o cualquier nombre completo que especifique el destino de la ejecución. Varios atributos que definen diferentes destinos de ejecución se pueden adjuntar a la misma. Algunas de nuestras pruebas siguen usando el paquete [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) en desuso que expone todas Q# las funciones y operaciones que terminan en `Test` el marco de [xUnit](https://xunit.github.io/) . Este paquete ya no es necesario para definir pruebas unitarias. 

La siguiente función se usa para garantizar que las <xref:microsoft.quantum.canon.fst> <xref:microsoft.quantum.canon.snd> funciones y devuelven los resultados correctos en un ejemplo representativo.
Si la salida de `Fst` o `Snd` es incorrecta, la `fail` instrucción se utiliza para hacer que la prueba genere un error.

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

Se pueden comprobar condiciones más complicadas mediante las técnicas de la [sección pruebas](xref:microsoft.quantum.libraries.diagnostics) de la guía de bibliotecas estándar.
Por ejemplo, las siguientes comprobaciones de prueba que `H(q); X(q); H(q);` , como llama, <xref:microsoft.quantum.canon.applywith> hace lo mismo que `Z(q)` .

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

Al agregar nuevas características, se recomienda agregar también nuevas pruebas para asegurarse de que la contribución realiza lo que se supone.
Esto ayuda al resto de la comunidad a mantener y desarrollar su característica y, en particular, ayuda a otros desarrolladores a saber que pueden confiar en su característica.

> [!NOTE]
> Esto también funciona de la otra manera.
> Si hay una característica existente que no tiene algunas pruebas, ayudarnos a agregar cobertura de pruebas supondrá una gran contribución a la comunidad.

Localmente, las pruebas unitarias se pueden ejecutar mediante el explorador de pruebas de Visual Studio o el `dotnet test` comando, para que pueda comprobar su contribución antes de abrir una solicitud de incorporación de cambios.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a>Cuándo se rechazará una solicitud de incorporación de cambios

A veces, rechazaremos la solicitud de incorporación de cambios para una contribución.
Si esto sucede, no significa que sea malo, ya que hay una serie de motivos por los que es posible que no podamos aceptar una contribución determinada.
Quizás lo más habitual es que una contribución a la comunidad de programación Quantum sea realmente buena, pero los repositorios del kit de desarrollo Quantum no son el lugar adecuado para desarrollarla.
En tales casos, le recomendamos encarecidamente que cree su propio repositorio---parte de la fuerza del kit de desarrollo de Quantum es que es fácil crear y distribuir sus propias bibliotecas con GitHub y NuGet.org, de la misma manera que se distribuyen las bibliotecas de Canon y química hoy en día.

En otras ocasiones, podemos rechazar una buena contribución simplemente porque todavía no estamos preparados para mantenerla y desarrollarla.
Puede ser difícil hacer todo, por lo que planeamos en qué características es mejor trabajar como guía.
Puede ser otro caso en el que la liberación de una característica como biblioteca de terceros puede tener mucho sentido.
Como alternativa, es posible que le pidamos su ayuda en la modificación de una característica para ajustarse mejor a nuestra guía básica, de modo que podamos hacer el mejor trabajo que podamos con ella.

También se pedirán cambios en una solicitud de incorporación de cambios si se requiere más documentación o pruebas unitarias para ayudarnos a usarlas, o si difiere lo suficiente en el estilo del resto de las Q# bibliotecas para que los usuarios puedan encontrar la característica.
En estos casos, intentaremos ofrecer algunos consejos en las revisiones de código sobre lo que se puede Agregar o cambiar para que podamos incluir su contribución.

Por último, no podemos aceptar contribuciones que causan el daño de la comunidad Quantum Computing, como se describe en el [código de conducta de código abierto de Microsoft](https://opensource.microsoft.com/codeofconduct/).
Queremos asegurarnos de que las contribuciones sirvan a toda la comunidad Quantum Computing, tanto en su actual diversidad actual como en el futuro, a medida que crezcan aún más.
Agradecemos su ayuda para alcanzar este objetivo.

## <a name="next-steps"></a>Pasos siguientes

Gracias por ayudarnos a que el kit de desarrollo de Quantum sea un excelente recurso para toda la comunidad de programación de Quantum.
Para obtener más información, continúe con la siguiente guía de Q# estilo.

> [!div class="nextstepaction"]
> [Más información sobre las Q# directrices de estilo](xref:microsoft.quantum.contributing.style)

En función del tipo de código que esté contribuyendo, es posible que tenga que tener en cuenta aspectos adicionales que pueden ayudarle a hacer que su contribución sea lo más conveniente para la comunidad como sea posible.

> [!div class="nextstepaction"]
> [Más información sobre los ejemplos de contribución](xref:microsoft.quantum.contributing.samples)
