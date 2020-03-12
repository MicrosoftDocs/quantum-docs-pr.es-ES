---
title: Archivo Léame de multimedia
description: Sugerencias para cargar imágenes
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 03/04/2020
ms.topic: readme
ms.openlocfilehash: a4922e28a8fc5ddfb4cbc80302e23869154234d8
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024192"
---
# <a name="readme"></a>ARCHIVO LÉAME
**Importante**: para que las imágenes se representen correctamente en modo oscuro, debe evitar las transparencias.
- En el caso de los archivos. jpg, no es necesario hacer nada, ya que el formato de archivo no admite elementos transparentes.
- En el caso de los archivos. png, debe agregar un fondo blanco o cambiar el valor del canal alfa a 100. La forma más fácil de hacerlo en Windows es abrir el archivo en Paint y guardarlo, overwritting el archivo original.
- En el caso de los archivos. SVG, debe agregar un rectángulo blanco en la capa inferior. Puede hacerlo con inkscape:
  - Abra el archivo. svg.
  - Seleccione la herramienta creador cuadrado y dibuje un rectángulo blanco encima de la figura original.
  - Seleccione la herramienta "seleccionar y transformar objetos"; para ello, haga clic en la flecha oscura o presione F1.
  - Con el rectángulo seleccionado, haga clic en el elemento de la barra de herramientas "bajar selección hacia abajo (final)".
  - Ajuste el rectángulo con el mouse o con las teclas de dirección.
