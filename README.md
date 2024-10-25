[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=16674305)

# Sistemas y Tecnología Web: Servidor
### Máster en Ingeniería Informática (Curso 24-25)
## Práctica: "Introduction to Systems Development" and Static Generators

**Alumna:** Rebeca Rodríguez Rodríguez (alu0101394763@ull.edu.es) - rrrguez

---

## Descripción y objetivos de la práctica
El objetivo de esta práctica es realizar un resumen de los conceptos más importantes del primer capítulo del libro: [**Developing Information Systems: Practical Guidance for IT Professionals**](https://ebookcentral-proquest-com.accedys2.bbtk.ull.es/lib/bull-ebooks/detail.action?docID=1713962#).

Este resumen deberá ser publicado como un post utilizando **Jekyll** y **GitHub Pages** para desplegar un sitio web con dicho informe.

Este repositorio parte de una plantilla predefinida, llamada [**Minimal Mistakes**](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/).

### Jekyll
**Jekyll** es un generador de sitios estático. Esta herramienta recibe texto escrito en un determinado lenguaje de marcado y utiliza _layouts_ para crear dichos sitios.

### GitHub Pages
**GitHub Pages** es otro generador estático de sitios que utiliza ficheros HTML, CSS y JavaScript directamente desde un reporitorio de GitHub y publica una página web a partir de ellos.

Esta herramienta está disponible para repositorios públicos, y también para repositorios privados si se tiene GitHub Pro, GitHub Team, GitHub Enterprise Cloud o GitHub Enterprise Server.

GitHub Pages se puede utilizar conjuntamente con Jekyll, puesto que ahora GitHub Pages usa GitHub Actions para ejecutar el Jekyll build. Solo hay que tener GitHub Actions habilitado en el repositorio en cuestión para usar el _workflow_ de Jekyll.

## Desarrollo de la práctica
A continuación, se exponen las acciones realizadas durante el desarrollo de la práctica.

### Primeros pasos
#### Instalación de las gemas necesarias
Se han utilizado los siguientes comandos:

```bash
bundle update
bundle install
```
Ha sido necesario ejecutar `bundle update` dado que `bundle install` daba problemas debido a la versión de Ruby.

Finalmente, se ha obtenido la siguiente salida:

![bundle update, install](/img/bundle%20update.PNG)

#### Servicio del sitio web
Se ha utilizado el siguiente comando para servir el sitio web:

```bash
rake serve
```

Este comando ha hecho que se reenvíe la página web el puerto 4001, como se puede ver a continuación:

![Puertos](/img/puertos.PNG)

Obteniendo el siguiente sitio:

![Salida rake serve](/img/salida%20rake.png)

#### Edición de `_posts/2022-10-01-informe.md`
Se ha editado el archivo [`_posts/2022-10-01-informe.md`](/_posts/2022-10-01-informe.md), de forma que ahora contiene el resumen solicitado.

Además, se le ha añadido el `permalink` "ejemplo", de forma que si se añade la cadena "`/intro2sd-rebeca-rodriguez-alu0101394763/ejemplo`" al final de la URL de la página una vez se arranque el servicio, se podrá visualizar los contenidos de este archivo.

#### Edición de _config.yml
1. Se ha editado el archivo [`_config.yml`](_config.yml), de forma que ahora contiene, entre otros:

    * En `baseurl`, la URL de este repositorio.
    * En `author`, mi nombre de usuario en GitHub.
    * En `social`, mis redes sociales.
    * En `footer`, mis links.
    * En `minimal_mistakes_skin`, `plum`.

2. Se ha añadido una nueva Jekyll Collection llamada "examples", a la que se le han añadido tres archivos de ejemplo:

    ![Jekyll Collection](/img/jekyll-collection.PNG)

    Estos archivos son mostrados en `_posts/2022-10-01-informe.md` usando el siguiente bloque de código Liquid:

    ```liquid
    {% for example in site.examples %}
        <h2><a href="{{ example.url }}">{{ example.title }}</a></h2>
        <p>{{ example.description }}</p>
    {% endfor %}
    ```

3. Se ha añadido un nuevo `default` para la colección "examples":

    ![Defaults](/img/defaults.PNG)

    Esto hará que, por defecto, los contenidos de la colección "examples" tengan el _layout_ `single`, que su autor sea `rrrguez`, y que pertenezcan a la categoría "Examples".

4. Se ha añadido un archivo [`/_data/examples.json`](/_data/examples.json) que contiene un conjunto de datos de ejemplo.
    Este archivo es accedido desde `/_posts/2022-10-01-informe.md` de la siguiente manera:

    ```liquid
    {% for example in site.data.examples %}
        <h2>{{ example.name }}</h2>
        <p>{{ example.description }}</p>
    {% endfor %}
    ```

Una vez guardados estos cambios en el archivo `_config.yml`, se para y rearranca el servidor mediante el comando `rake serve`, obteniendo ahora la siguiente página:

![Resultado](/img/intro2sd.png)

### Despliegues
#### GitHub Pages
Para realizar el despliegue en GitHub Pages, se va a utilizar una rama `gh-pages`. Esta rama se puede crear desde la línea de comandos de la siguiente manera:

```bash
git branch gh-pages
git checkout gh-pages
```

En este caso, no ha sido necesario realizar ningún otro paso adicional, puesto que se ha partido de un repositorio existente que ya estaba configurado.

Si se navega al apartado "Settings" del repositorio de la práctica, en la sección _Pages_ de "Code and automation", se podrá ver el enlace al sitio desplegado:

![Pages](/img/pages.png)

#### Netlify && Vercel
Se ha realizado un segundo despliegue en Netlify.

Como Netlify no forma parte del paquete de GitHub, ha sido necesario cambiar la visibilidad del repositorio a público.

Para realizar el despliegue, se han seguido los siguientes pasos:

1. Comprobación de que la configuración del repositorio es la adecuada.

2. Creación de una cuenta en [Netlify](https://www.netlify.com).

3. Conexión de mi cuenta con GitHub y selección del repositorio de la práctica, dando a Netlify la autorización requerida.

4. Despliegue de la página web.

    ![Despliegue sin errores](/img/deploy-netlify.png)

    ![Página desplegada](/img/netlify-pag-desplegada.png)

    > [!NOTE]
    > La página desplegada aparece sin estilos porque, después de numerosos problemas con las dependencias del proyecto en el despliegue, finalmente conseguí que este se pudiese completar sin errores comentando las líneas relativas a Sass en el archivo `_config.yml` de la rama `netlify`, que es desde donde se ha realizado el despliegue.

### Personalización de la página `404.md`
Se ha personalizado la página de error [`404.md`](/_pages/404.md) tomando como inspiración la descrita en los [apuntes](https://ull-mii-sytws.github.io/temas/web/jekyll-404.html).

En este caso, se mostrará un mensaje de error y se mostrarán imágenes de perritos aleatorias obtenidas de [The Dog API](https://thedogapi.com). Por ejemplo:

![The Dog API](/img/dog-api.png)

### Página personal
Con los conocimientos adquiridos en los pasos anteriores, se ha desarrollado una página personal en GitHub.

Esta página ha sido enlazada desde mi perfil de GitHub, de forma que puede ser fácilmente accesible desde allí.