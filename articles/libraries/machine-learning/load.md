---
title: Carga de datos de clásica
description: Aprenda a cargar su propio conjunto de información para entrenar un modelo clasificador con el Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: 15e63ced6223759a332ce22a43c133a7899f482a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909966"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="9a1ee-103">Carga y clasificación de sus propios conjuntos de valores</span><span class="sxs-lookup"><span data-stu-id="9a1ee-103">Load and classify your own datasets</span></span>

<span data-ttu-id="9a1ee-104">En este breve tutorial, vamos a aprender a cargar su propio conjunto de información para entrenar un modelo clasificador con Quantum Development Kit (QDK).</span><span class="sxs-lookup"><span data-stu-id="9a1ee-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="9a1ee-105">Se recomienda encarecidamente el uso de un formato de serialización normalizado, como [archivos JSON](https://en.wikipedia.org/wiki/JSON) , para almacenar los datos.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="9a1ee-106">Estos formatos ofrecen una alta compatibilidad con marcos diferentes como Python y el ecosistema de .NET.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="9a1ee-107">En concreto, se recomienda usar nuestra plantilla para cargar los datos, para que pueda copiar y pegar el código directamente desde los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="9a1ee-108">Plantilla para cargar los conjuntos de valores</span><span class="sxs-lookup"><span data-stu-id="9a1ee-108">Template for loading your datasets</span></span>

<span data-ttu-id="9a1ee-109">Supongamos que tenemos un conjunto de elementos de entrenamiento $ (x, y) $ de size $N = $2, donde cada instancia $x _i $ de $x $ tiene tres características: $x _ {I1} $, $x _ {I2} $ y $x _ {i3} $.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="9a1ee-110">El conjunto de de validación tiene la misma estructura.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="9a1ee-111">Estos conjuntos se pueden representar mediante un archivo `data.json` similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a1ee-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a><span data-ttu-id="9a1ee-112">Ejemplo de uso de la plantilla</span><span class="sxs-lookup"><span data-stu-id="9a1ee-112">Example using the template</span></span>

<span data-ttu-id="9a1ee-113">Supongamos que tenemos un conjunto de filas pequeño con los altos y pesos de los distintos gatos y perros.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="9a1ee-114">Este conjunto de DataSet es muy pequeño para entrenar un modelo, pero lo suficiente como para mostrar el proceso de carga de un conjunto de DataSet.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="9a1ee-115">Alto (m)</span><span class="sxs-lookup"><span data-stu-id="9a1ee-115">Height (m)</span></span> | <span data-ttu-id="9a1ee-116">Peso (kg)</span><span class="sxs-lookup"><span data-stu-id="9a1ee-116">Weight (kg)</span></span> | <span data-ttu-id="9a1ee-117">Animal</span><span class="sxs-lookup"><span data-stu-id="9a1ee-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="9a1ee-118">0,54</span><span class="sxs-lookup"><span data-stu-id="9a1ee-118">0.54</span></span>      | <span data-ttu-id="9a1ee-119">30</span><span class="sxs-lookup"><span data-stu-id="9a1ee-119">30</span></span>         | <span data-ttu-id="9a1ee-120">Foto</span><span class="sxs-lookup"><span data-stu-id="9a1ee-120">Dog</span></span>    |
| <span data-ttu-id="9a1ee-121">0,30</span><span class="sxs-lookup"><span data-stu-id="9a1ee-121">0.30</span></span>      | <span data-ttu-id="9a1ee-122">8</span><span class="sxs-lookup"><span data-stu-id="9a1ee-122">8</span></span>          | <span data-ttu-id="9a1ee-123">Catalítica</span><span class="sxs-lookup"><span data-stu-id="9a1ee-123">Cat</span></span>    |
| <span data-ttu-id="9a1ee-124">0,91</span><span class="sxs-lookup"><span data-stu-id="9a1ee-124">0.91</span></span>      | <span data-ttu-id="9a1ee-125">44</span><span class="sxs-lookup"><span data-stu-id="9a1ee-125">44</span></span>         | <span data-ttu-id="9a1ee-126">Foto</span><span class="sxs-lookup"><span data-stu-id="9a1ee-126">Dog</span></span>    |
| <span data-ttu-id="9a1ee-127">0,86</span><span class="sxs-lookup"><span data-stu-id="9a1ee-127">0.86</span></span>      | <span data-ttu-id="9a1ee-128">31</span><span class="sxs-lookup"><span data-stu-id="9a1ee-128">31</span></span>          | <span data-ttu-id="9a1ee-129">Foto</span><span class="sxs-lookup"><span data-stu-id="9a1ee-129">Dog</span></span>    |
| <span data-ttu-id="9a1ee-130">0,32</span><span class="sxs-lookup"><span data-stu-id="9a1ee-130">0.32</span></span>      | <span data-ttu-id="9a1ee-131">5</span><span class="sxs-lookup"><span data-stu-id="9a1ee-131">5</span></span>         | <span data-ttu-id="9a1ee-132">Catalítica</span><span class="sxs-lookup"><span data-stu-id="9a1ee-132">Cat</span></span>    |
| <span data-ttu-id="9a1ee-133">0,25</span><span class="sxs-lookup"><span data-stu-id="9a1ee-133">0.25</span></span>      | <span data-ttu-id="9a1ee-134">4</span><span class="sxs-lookup"><span data-stu-id="9a1ee-134">4</span></span>          | <span data-ttu-id="9a1ee-135">Catalítica</span><span class="sxs-lookup"><span data-stu-id="9a1ee-135">Cat</span></span>    |

<span data-ttu-id="9a1ee-136">El proceso es:</span><span class="sxs-lookup"><span data-stu-id="9a1ee-136">The process is:</span></span>

- <span data-ttu-id="9a1ee-137">En primer lugar, es necesario separar el conjunto de conocimientos en entrenamiento y validación.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="9a1ee-138">En este caso, podemos realizar solo los tres primeros ejemplos de entrenamiento y el resto de ejemplos para la validación.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="9a1ee-139">En general, se recomienda obtener un ejemplo aleatorio del conjunto de datos de entrenamiento y validación para evitar los sesgos no deseados en los datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="9a1ee-140">En segundo lugar, es necesario asignar una etiqueta numérica a cada clase.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="9a1ee-141">Tenga en cuenta que, por el momento, la biblioteca QML solo tiene problemas de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="9a1ee-142">Por lo tanto, asignaremos la etiqueta 0 a la clase `Dog` y el número 1 a la clase `Cat`.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="9a1ee-143">Por último, se rellena la plantilla con los datos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="9a1ee-144">Tenga en cuenta que para conjuntos de datos grandes, debe crear un script pequeño para generar automáticamente la plantilla a partir de su conjunto de datos concreto.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="9a1ee-145">Este script dependerá del formato original del conjunto de DataSet.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="9a1ee-146">Para nuestro conjunto de archivos, el archivo `data.json` es:</span><span class="sxs-lookup"><span data-stu-id="9a1ee-146">For our dataset the `data.json` file is:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a><span data-ttu-id="9a1ee-147">Cargar los datos</span><span class="sxs-lookup"><span data-stu-id="9a1ee-147">Loading the data</span></span>

<span data-ttu-id="9a1ee-148">Una vez que los datos se serializan como un archivo JSON, puede cargarlos en mediante las bibliotecas JSON proporcionadas con el lenguaje de host que prefiera.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="9a1ee-149">Python</span><span class="sxs-lookup"><span data-stu-id="9a1ee-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="9a1ee-150">Python proporciona el [paquete de `json` integrado](https://docs.python.org/3.7/library/json.html) para trabajar con datos serializados de JSON:</span><span class="sxs-lookup"><span data-stu-id="9a1ee-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="9a1ee-151">C#</span><span class="sxs-lookup"><span data-stu-id="9a1ee-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="9a1ee-152">La plataforma .NET Core proporciona el [paquete de`System.Text.Json`](https://www.nuget.org/packages/System.Text.Json) para trabajar con datos serializados de JSON:</span><span class="sxs-lookup"><span data-stu-id="9a1ee-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="whats-next"></a><span data-ttu-id="9a1ee-153">¿Qué sigue?</span><span class="sxs-lookup"><span data-stu-id="9a1ee-153">What's next?</span></span>

<span data-ttu-id="9a1ee-154">Ahora ya está listo para empezar a ejecutar sus propios experimentos con sus propios conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="9a1ee-155">Pruebe diferentes clasificadores y conjuntos de archivos y contribuya a la comunidad compartiendo sus resultados.</span><span class="sxs-lookup"><span data-stu-id="9a1ee-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
