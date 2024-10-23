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
Se ha editado el archivo [_posts/2022-10-01-informe.md](/_posts/2022-10-01-informe.md), de forma que ahora contiene el resumen solicitado.

#### Edición de _config.yml
Se ha editado el archivo [`_config.yml`](_config.yml), de forma que ahora contiene, entre otros:

* En `baseurl`, la URL de este repositorio.
* En `author`, mi nombre de usuario en GitHub.
* En `social`, mis redes sociales.
* En `footer`, mis links.
* En `minimal_mistakes_skin`, `plum`.
