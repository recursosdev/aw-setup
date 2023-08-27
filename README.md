# Configuración del entorno de trabajo

>*Este documento README está escrito en lenguaje [MARKDOWN](https://www.markdownguide.org/) y podemos ver un tutorial [aquí](https://tutorialmarkdown.com/)<img src="images/external.svg" style="max-width:16px;">.*
>  
>*La configuración básica del entorno de trabajo para desarrollo nos permite tener ordenado nuestro proyecto.*

---

Esta configuración se pauta con el equipo, pero vamos a utilizar las herramientas más conocidas.

* Creación del directorio de trabajo
* Sincronizar o abrir el directorio de trabajo con el IDE
* Inicializar control de versiones con GIT y crear un repositorio remoto para alojar nuestro proyecto
* Inicializar npm y añadir configuraciones
* Estructurar los directorios de trabajo
* Instalar las dependencias de desarrollo necesarias

## Creación del directorio de trabajo

En este paso vamos a crear el directorio o carpeta en nuestra computadora que será nuestro directorio de trabajo.

## Sincronizar o abrir el directorio de trabajo con el IDE

Vincularemos el directorio con nuestro IDE. Aquí utilizaremos [Visual Estudio Code](https://code.visualstudio.com/)

Abriremos nuestro proyecto en este IDE.

Abriremos la terminal desde el menu "Terminal>New Terminal" o "Terminal>Nueva terminal". También lo podremos hacer con Ctrl + Shift + `

## Inicializar control de versiones con GIT y crear un repositorio remoto para alojar nuestro proyecto

Desde la terminal de VSCode o Code (distintos nombres de Visual Estudio Code) inicializaremos nuestro proyecto con un sofware de control de versiones, en nuestro caso [GIT](https://git-scm.com/)

Si no lo tenemos instalado, seguiremos [esta guía](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Instalaci%C3%B3n-de-Git)

### Inicializar repositorio

Pra inicializar un repositorio utiizaremos la consola de VSCode. Sobre el directorio de trabajo actual, en la consola escribiremos:

```bash
git init
```

Git creará una carpeta llamada `.git`.

Todo directorio que comience con un punto (*`.nombre_carpeta`*) el sistema operativo lo ocultará. Para verlo, debemos configurarlo y dependerá del sistema operativo que tengamos instalado:

* Windows [ver](https://support.microsoft.com/es-es/windows/mostrar-archivos-ocultos-0320fe58-0117-fd59-6851-9b7f9840fdb2#:~:text=Selecciona%20el%20bot%C3%B3n%20Inicio%20y,%2C%20a%20continuaci%C3%B3n%2C%20selecciona%20Aceptar.)
* Linux utilizando el atajo de teclado  `Ctrl + h` (Manteniendo apretado -> Control y la letra H)
* Mac utilizando el atajo de teclado `cmd + shift + .` (Manteniendo apretado Comando, shift [mayúsculas] y tecla del punto)

### Configuraciones básicas

Debemos decirle a git quienes somos y lo haremos escribiendo esto en la consola:

```bash
git config user.name "tu_nombre_de_usuario"
```

```bash
git config user.email "tu_email"
```

Todo esto se guarda en un archivo de configuración del proyecto dentro del directorio `.git` en donde se encuentra el archivo `config`

Además, crearemos un archivo llamado `.gitignore` que servirá para que Git no suba ciertos tipos de archivos al repositorio remoto, por ejemplo, `node_modules`, y lo haremos agregando al archivo el nombre de esta carpeta `node_modules/`. Cada archivo o directorio que queremos **ignorar**, debemos escribirlo en una nueva línea.

>Para configurar usuario y email globalmente, podemos hacerlo con la bandera o *flag* `--global`
>Esto es útil cuando vamos a utilizar los mismos datos siempre.
>
>```bash
>git congig --global user.name "tu_nombre_de_usuario"
>git congig --global user.email "tu_email"
>```

Podemos ver un tutorial para el uso de Git [aquí](https://www.atlassian.com/es/git/tutorials/what-is-version-control)

## Inicializar npm y añadir configuraciones

Conjuntamente con Nodejs se instala Npm, que es un gestor de paquetes de Nodejs y que utilizaremos para nuestros proyectos.

Para trabajar con npm debemos tener Node instalado en nuestro sistema operativo.

>*Existen otros gestores de paquetes de node llamados [Yarn](https://yarnpkg.com/) y [pNpm](https://pnpm.io/)*

Para instalar Nodejs y Npm en **Windows** lo podemos hacer siguiendo este [video](https://www.youtube.com/watch?v=Z-Ofqd2yBCc), que es la manera recomendada, ya que nos permite utilizar varias versiones de Node y Npm en nuestra computadora.

O de la manera tradicional [descargando Nodejs](https://nodejs.org/es/download) instalando la versión estable LTS (Long Time Support) para el sitema operativo que tengamos.

Para inicializar npm en nuestro proyecto lo hacremos de la siguiente manera:

```bash
npm init
```

Y nos va a hacer una serie de preguntas, esto creará un archivo llamado `package.json` que será la confuguración de nuestro proyecto.

>Podemos ver cómo es y que datos van en el archivo `package.json` [aquí](https://lenguajejs.com/npm/administracion/package-json/).

## Estructurar los directorios de trabajo

No existe una manera correcta para la estructura de un proyecto, pero podemos seguir algunos lineamientos muy utilizados.

Utilicemos uno básico por ahora:

```text
/mi_proyecto
    /src
        /assets
            /css
            /js
            /images
        index.html
```

Una vez hechas las instalaciones quedará algo así:

```text
/mi_proyecto
    .git
    /node_modules/
    /src/
        /assets/
            /css/
            /js/
            /images/
        index.html
    .gitignore
    package-lock.json
    package.json
```

Podemos encontrar algunos archivos o carpetas más, pero esto sería lo básico.

Para saber más, [ver este artículo](https://lenguajejs.com/npm/administracion/crear-nuevo-proyecto/).

## Instalar las dependencias de desarrollo necesarias

Por el momento instalaremos un paquete que nos permitirá disponer de un servidor local para comezar a trabajar y probar nuestra aplicación web: `five-server`

```bash
npm install --save-dev five-server
```

El comando anterior instala la dependencia como dependencia de desarrollo, esto significa que no es necesaria en producción.
