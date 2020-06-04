---
title: Carga de datos de clásica
description: Aprenda a cargar su propio conjunto de información para entrenar un modelo clasificador con el Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: efa4a65a489446cbef48507d0b02a932da74c71c
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327669"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="48e1f-103">Carga y clasificación de sus propios conjuntos de valores</span><span class="sxs-lookup"><span data-stu-id="48e1f-103">Load and classify your own datasets</span></span>

<span data-ttu-id="48e1f-104">En este breve tutorial, vamos a aprender a cargar su propio conjunto de información para entrenar un modelo clasificador con Quantum Development Kit (QDK).</span><span class="sxs-lookup"><span data-stu-id="48e1f-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="48e1f-105">Se recomienda encarecidamente el uso de un formato de serialización normalizado, como [archivos JSON](https://en.wikipedia.org/wiki/JSON) , para almacenar los datos.</span><span class="sxs-lookup"><span data-stu-id="48e1f-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="48e1f-106">Estos formatos ofrecen una alta compatibilidad con marcos diferentes como Python y el ecosistema de .NET.</span><span class="sxs-lookup"><span data-stu-id="48e1f-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="48e1f-107">En concreto, se recomienda usar nuestra plantilla para cargar los datos, para que pueda copiar y pegar el código directamente desde los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="48e1f-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="48e1f-108">Plantilla para cargar los conjuntos de valores</span><span class="sxs-lookup"><span data-stu-id="48e1f-108">Template for loading your datasets</span></span>

<span data-ttu-id="48e1f-109">Supongamos que tenemos un conjunto de elementos de entrenamiento $ (x, y) $ de size $N = $2, donde cada instancia $x _i $ de $x $ tiene tres características: $x _ {I1} $, $x _ {I2} $ y $x _ {i3} $.</span><span class="sxs-lookup"><span data-stu-id="48e1f-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="48e1f-110">El conjunto de de validación tiene la misma estructura.</span><span class="sxs-lookup"><span data-stu-id="48e1f-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="48e1f-111">Estos conjuntos se pueden representar con un `data.json` archivo similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="48e1f-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

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

### <a name="example-using-the-template"></a><span data-ttu-id="48e1f-112">Ejemplo de uso de la plantilla</span><span class="sxs-lookup"><span data-stu-id="48e1f-112">Example using the template</span></span>

<span data-ttu-id="48e1f-113">Supongamos que tenemos un conjunto de filas pequeño con los altos y pesos de los distintos gatos y perros.</span><span class="sxs-lookup"><span data-stu-id="48e1f-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="48e1f-114">Este conjunto de DataSet es muy pequeño para entrenar un modelo, pero lo suficiente como para mostrar el proceso de carga de un conjunto de DataSet.</span><span class="sxs-lookup"><span data-stu-id="48e1f-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="48e1f-115">Alto (m)</span><span class="sxs-lookup"><span data-stu-id="48e1f-115">Height (m)</span></span> | <span data-ttu-id="48e1f-116">Peso (kg)</span><span class="sxs-lookup"><span data-stu-id="48e1f-116">Weight (kg)</span></span> | <span data-ttu-id="48e1f-117">Animal</span><span class="sxs-lookup"><span data-stu-id="48e1f-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="48e1f-118">0,54</span><span class="sxs-lookup"><span data-stu-id="48e1f-118">0.54</span></span>      | <span data-ttu-id="48e1f-119">30</span><span class="sxs-lookup"><span data-stu-id="48e1f-119">30</span></span>         | <span data-ttu-id="48e1f-120">Foto</span><span class="sxs-lookup"><span data-stu-id="48e1f-120">Dog</span></span>    |
| <span data-ttu-id="48e1f-121">0,30</span><span class="sxs-lookup"><span data-stu-id="48e1f-121">0.30</span></span>      | <span data-ttu-id="48e1f-122">8</span><span class="sxs-lookup"><span data-stu-id="48e1f-122">8</span></span>          | <span data-ttu-id="48e1f-123">Catalítica</span><span class="sxs-lookup"><span data-stu-id="48e1f-123">Cat</span></span>    |
| <span data-ttu-id="48e1f-124">0,91</span><span class="sxs-lookup"><span data-stu-id="48e1f-124">0.91</span></span>      | <span data-ttu-id="48e1f-125">44</span><span class="sxs-lookup"><span data-stu-id="48e1f-125">44</span></span>         | <span data-ttu-id="48e1f-126">Foto</span><span class="sxs-lookup"><span data-stu-id="48e1f-126">Dog</span></span>    |
| <span data-ttu-id="48e1f-127">0,86</span><span class="sxs-lookup"><span data-stu-id="48e1f-127">0.86</span></span>      | <span data-ttu-id="48e1f-128">31</span><span class="sxs-lookup"><span data-stu-id="48e1f-128">31</span></span>          | <span data-ttu-id="48e1f-129">Foto</span><span class="sxs-lookup"><span data-stu-id="48e1f-129">Dog</span></span>    |
| <span data-ttu-id="48e1f-130">0,32</span><span class="sxs-lookup"><span data-stu-id="48e1f-130">0.32</span></span>      | <span data-ttu-id="48e1f-131">5</span><span class="sxs-lookup"><span data-stu-id="48e1f-131">5</span></span>         | <span data-ttu-id="48e1f-132">Catalítica</span><span class="sxs-lookup"><span data-stu-id="48e1f-132">Cat</span></span>    |
| <span data-ttu-id="48e1f-133">0,25</span><span class="sxs-lookup"><span data-stu-id="48e1f-133">0.25</span></span>      | <span data-ttu-id="48e1f-134">4</span><span class="sxs-lookup"><span data-stu-id="48e1f-134">4</span></span>          | <span data-ttu-id="48e1f-135">Catalítica</span><span class="sxs-lookup"><span data-stu-id="48e1f-135">Cat</span></span>    |

<span data-ttu-id="48e1f-136">El proceso es:</span><span class="sxs-lookup"><span data-stu-id="48e1f-136">The process is:</span></span>

- <span data-ttu-id="48e1f-137">En primer lugar, es necesario separar el conjunto de conocimientos en entrenamiento y validación.</span><span class="sxs-lookup"><span data-stu-id="48e1f-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="48e1f-138">En este caso, podemos realizar solo los tres primeros ejemplos de entrenamiento y el resto de ejemplos para la validación.</span><span class="sxs-lookup"><span data-stu-id="48e1f-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="48e1f-139">En general, se recomienda obtener un ejemplo aleatorio del conjunto de datos de entrenamiento y validación para evitar los sesgos no deseados en los datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="48e1f-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="48e1f-140">En segundo lugar, es necesario asignar una etiqueta numérica a cada clase.</span><span class="sxs-lookup"><span data-stu-id="48e1f-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="48e1f-141">Tenga en cuenta que, por el momento, la biblioteca QML solo tiene problemas de clasificación binaria.</span><span class="sxs-lookup"><span data-stu-id="48e1f-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="48e1f-142">Por lo tanto, asignaremos la etiqueta 0 a la clase `Dog` y el número 1 a la clase `Cat` .</span><span class="sxs-lookup"><span data-stu-id="48e1f-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="48e1f-143">Por último, se rellena la plantilla con los datos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="48e1f-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="48e1f-144">Tenga en cuenta que para conjuntos de datos grandes, debe crear un script pequeño para generar automáticamente la plantilla a partir de su conjunto de datos concreto.</span><span class="sxs-lookup"><span data-stu-id="48e1f-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="48e1f-145">Este script dependerá del formato original del conjunto de DataSet.</span><span class="sxs-lookup"><span data-stu-id="48e1f-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="48e1f-146">Para nuestro conjunto de `data.json` archivos, el archivo es:</span><span class="sxs-lookup"><span data-stu-id="48e1f-146">For our dataset the `data.json` file is:</span></span>

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

## <a name="loading-the-data"></a><span data-ttu-id="48e1f-147">Carga de los datos</span><span class="sxs-lookup"><span data-stu-id="48e1f-147">Loading the data</span></span>

<span data-ttu-id="48e1f-148">Una vez que los datos se serializan como un archivo JSON, puede cargarlos en mediante las bibliotecas JSON proporcionadas con el lenguaje de host que prefiera.</span><span class="sxs-lookup"><span data-stu-id="48e1f-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="48e1f-149">Python</span><span class="sxs-lookup"><span data-stu-id="48e1f-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="48e1f-150">Python proporciona el [ `json` paquete integrado](https://docs.python.org/3.7/library/json.html) para trabajar con datos serializados de JSON:</span><span class="sxs-lookup"><span data-stu-id="48e1f-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="48e1f-151">C#</span><span class="sxs-lookup"><span data-stu-id="48e1f-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="48e1f-152">La plataforma .NET Core proporciona el [ `System.Text.Json` paquete](https://www.nuget.org/packages/System.Text.Json) para trabajar con datos serializados de JSON:</span><span class="sxs-lookup"><span data-stu-id="48e1f-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="48e1f-153">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="48e1f-153">Next steps</span></span>

<span data-ttu-id="48e1f-154">Ahora ya está listo para empezar a ejecutar sus propios experimentos con sus propios conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="48e1f-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="48e1f-155">Pruebe diferentes clasificadores y conjuntos de archivos y contribuya a la comunidad compartiendo sus resultados.</span><span class="sxs-lookup"><span data-stu-id="48e1f-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
