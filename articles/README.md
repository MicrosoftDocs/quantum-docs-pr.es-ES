# <a name="articles"></a>Artículos

En este directorio puede encontrar los artículos de la documentación del kit de desarrollo de Quantum. Este directorio contiene:

- **Directorios de artículos**: contiene los artículos de cada sección de la documentación. En estos directorios puede encontrar el contenido siguiente:
  
  - Cada directorio contiene un `toc.yml` archivo para mostrar el contenido del directorio en la tabla de contenido principal (TDC).
  - Artículos de Markdown que contienen la documentación de. Estos artículos deben seguir las instrucciones de la [Guía del colaborador de Microsoft docs](https://docs.microsoft.com/en-us/contribute/).
  - Artículos subdirectorios. Estos subdirectorios también deben contener su propio `toc.yml` archivo.

> :p encil: aunque es posible hacer referencia a los `*.md` archivos directamente en el `TOC.yml` archivo principal, para mantener las cosas ordenadas, solo se hace referencia a ellas desde el `toc.yml` directorio actual.

- ** `TOC.yml` Archivo de tabla de contenido (TOC) principal**: en este archivo, las secciones de la TDC del sitio web se enumeran junto con la referencia al `toc.yml` archivo principal del directorio de cada sección.
- **`index.yml`** YAML con la configuración de la página de aterrizaje de la documentación.
- **`\media`**: Directorio donde se almacenan todas las imágenes que se usan en la documentación. Contiene un `\media\src` subdirectorio para almacenar los archivos de origen de las imágenes.
- **Archivos de licencia**: archivos que contienen licencias legales
- **Archivos técnicos**: archivos que contienen macros y metadatos.

## <a name="guidelines"></a>Instrucciones

Algunas directrices generales sobre la organización de este directorio para los colaboradores:

- Cada directorio o subdirectorio debe contener su propio `toc.yml` archivo en el que se hace referencia a los artículos del mismo nivel o los `toc.yml` archivos de sus directorios secundarios.
- La organización de los directorios del repositorio debe ser lo más cercana posible a la organización de la tabla de contenido del sitio web de documentación.
- Todas las imágenes deben almacenarse en `articles\media` y no en la carpeta artículos.
- Los títulos de los artículos, los nombres de la TDC y el *UID* de los metadatos deben estar lo más cerca posible entre ellos y representar claramente el encabezado H1 del documento de Markdown.

## <a name="adding-images"></a>Agregar imágenes

Para que las imágenes se representen correctamente en modo oscuro, debe evitar las transparencias.
- En `*.jpg` el caso de los archivos no es necesario hacer nada, ya que el formato de archivo no admite elementos transparentes.
- En `*.png` el caso de los archivos, debe agregar un fondo blanco o cambiar el valor del canal alfa a 100. La forma más fácil de hacerlo en Windows es abrir el archivo en Paint y guardarlo, sobrescribiendo el archivo original.
- `*.svg`En el caso de los archivos, debe agregar un rectángulo blanco en la capa inferior. Puede hacerlo con inkscape:
  - Abra el archivo `*.svg` .
  - Seleccione la herramienta creador cuadrado y dibuje un rectángulo blanco encima de la figura original.
  - Seleccione la herramienta "seleccionar y transformar objetos"; para ello, haga clic en la flecha oscura o presione F1.
  - Con el rectángulo seleccionado, haga clic en el elemento de la barra de herramientas "bajar selección hacia abajo (final)".
  - Ajuste el rectángulo con el mouse o con las teclas de dirección.
