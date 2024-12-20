[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=16674305)

[![pages-build-deployment](https://github.com/ULL-MII-SYTWS-2425/intro2sd-rebeca-rodriguez-alu0101394763/actions/workflows/pages/pages-build-deployment/badge.svg?branch=gh-pages)](https://github.com/ULL-MII-SYTWS-2425/intro2sd-rebeca-rodriguez-alu0101394763/actions/workflows/pages/pages-build-deployment)

[![Netlify Status](https://api.netlify.com/api/v1/badges/2544b7a0-0bf3-4e13-81a2-84a67e633a22/deploy-status)](https://app.netlify.com/sites/intro2sd-rebeca-rodriguez/deploys)

# Sistemas y Tecnología Web: Servidor
### Máster en Ingeniería Informática (Curso 24-25)
## Práctica: Jekyll Search

**Alumna:** Rebeca Rodríguez Rodríguez (alu0101394763@ull.edu.es) - rrrguez

---

## Descripción y objetivos de la práctica
El objetivo de esta práctica es incoporar la capacidad de búsqueda al sitio web desarrollado en la Práctica: <ins>"Introduction to Systems Development" and Static Generators</ins>.

En la siguiente lista se recogen los principales requisitos de la práctica:
* Capacidad para buscar en todos los ficheros, lo que incluye no solo los de los posts, sino también los de las páginas.

* Capacidad para admitir expresiones regulares.

* Aparición de los resultados conforme se vaya tecleando.

* Visualización de una lista de enlaces a los ficheros que contienen la expresión buscada y un resumen de las primeros caracteres del fichero.

* Lectura y resumen en un post del Capítulo 2 (*Lifecycle types and their rationals*, por Lynda Girvan) del libro *Developing Information Systems*, editado por James Cadle.

## Desarrollo de la práctica

### Primeros pasos
En primer lugar, se ha realizado el resumen solicitado y se ha almacenado como post en el fichero [`/_posts/2024-11-02-chapter2.md`](/_posts/2024-11-02-chapter2.md).

### `search.json`
A continuación, se ha definido el fichero [`/assets/src/search.json`](/assets/src/search.json), en el que se ha hecho uso del lenguaje de plantillas Liquid para generar en tiempo de construcción la información de todas y cada una de las páginas del sitio web. Esto se hace con el siguiente comando:

```bash
bundle exec jekyll build
```

La ejecución del comando anterior resultará en un fichero `/_site/assets/src/search.json` que contendrá la información de todas las páginas en formato JSON, tal como se muestra en el ejemplo a continuación:

```json
[
    {
        "title": "Introduction to Systems Development",
        "excerpt": "Systems development is the process of transforming business requirements into an operational IT system through a structured sequence of stages. These stages typically include the following:\n",
        "content": "Systems development is the process of transforming business requirements into an operational IT system through a structured sequence of stages. These stages typically include the following:\n\n\n  \n    Feasibility studies.\n  \n  \n    Requirements engineering.\n  \n  \n    System design.\n  \n  \n    Software development.\n  \n  \n    Testing.\n  \n  \n    Implementation.\n  \n\n\nThe goal is to create more reliable and manageable systems, reducing reliance on individual developer competence by introducing standardized processes.\n\n\n\nThe following are the relationships of systems development to other disciplines:\n\n\n  \n    Project management plays a crucial role in coordinating resources and ensuring that all stakeholders are aligned with the project goals.\n  \n  \n    Business analysis focuses on identifying business problems and opportunities, often involving IT solutions, and managing system requirements.\n  \n  \n    Systems architecture involves designing a coherent IT infrastructure to support organizational growth.\n  \n  \n    Testing ensures that the developed system functions as expected, even though no system can be guaranteed to be completely error-free.\n  \n  \n    Configuration management tracks system components and changes.\n  \n  \n    Quality control processes and assurance ensures the system meets predefined standards and establishes standards, respectively.\n  \n  \n    Service management involves maintaining IT services and infrastructure, ensuring smooth operations and continuous support after the system is deployed.\n  \n\n\n\n\nOn the other hand, offshoring and outsourcing have significantly influenced systems development.\n\nOffshoring involves leveraging lower-cost, high-quality development resources in other countries, like India or Eastern European nations, while outsourcing refers to handing over development work to specialized IT firms.\n\nBoth practices offer cost savings but come with potential downsides, such as communication challenges (in offshoring) and a loss of direct control over critical systems (in outsourcing).\n\n\n\n\n  Ahmed, Tahir, et al. Developing Information Systems : Practical guidance for IT professionals, edited by James Cadle, BCS Learning &amp; Development Limited, 2014. ProQuest Ebook Central, http://ebookcentral.proquest.com/lib/bull-ebooks/detail.action?docID=1713962.\n\n\n\n\nA continuación, se muestran los contenidos de la colección examples:\n\nEjemplo 1\nEjemplo 1 de la colección 'examples'\n\nEjemplo 2\nEjemplo 2 de la colección 'examples'\n\nEjemplo 3\nEjemplo 3 de la colección 'examples'\n\n\n\nY se accede al archivo /_data/examples.json:\n\nExample 1\nEste es el ejemplo 1\n\nExample 2\nEste es el ejemplo 2\n\nExample 3\nEste es el ejemplo 3\n",
        "url": "/intro2sd-rebeca-rodriguez-alu0101394763//chapter1"
    },
    
    {
        "title": "Lifecycle types and their rationals",
        "excerpt": "Modelos y Enfoques de Desarrollo de Software\n",
        "content": "Modelos y Enfoques de Desarrollo de Software\nLos enfoques de desarrollo de software varían en sus características, aplicabilidad y adaptabilidad a diferentes tipos de proyectos. Entre los modelos más destacados se encuentran:\n\n\n  Modelos Evolutivos e Iterativos:\n\n\n\n  \n    Spiral: Propone un desarrollo iterativo basado en prototipos y gestión de riesgos. En cada ciclo se revisan objetivos, se identifican riesgos, se desarrollan prototipos y se planifican iteraciones. Este modelo es efectivo para proyectos de alta complejidad, aunque requiere una gestión rigurosa para evitar incrementos en el alcance.\n  \n  \n    DSDM: Enfocado en iteraciones rápidas y entregas incrementales, DSDM aplica principios de negocio, colaboración y control, siendo adecuado para proyectos orientados al negocio. Se le percibe tanto como un marco de gestión de proyectos, lo que puede dificultar su implementación en desarrollos de menor envergadura.\n  \n  \n    Scrum: Popular en equipos pequeños, usa ciclos cortos llamados “sprints” para entregar versiones funcionales del producto. Si bien facilita la adaptación a cambios, requiere alta colaboración del cliente y puede ser difícil de escalar en proyectos complejos.\n  \n\n\n\n  \n    Modelos Ágiles:\nEl Agile Manifesto de 2001 impulsó un enfoque centrado en la flexibilidad, priorizando la interacción sobre la documentación y la colaboración con el cliente sobre la negociación contractual. Las metodologías ágiles funcionan bien en entornos colaborativos, aunque enfrentan dificultades en equipos grandes, sistemas complejos o proyectos con altos requisitos regulatorios. Estos métodos pueden combinarse con enfoques tradicionales para cumplir con normas estrictas.\n  \n  \n    Modelos Estructurados y Lineales:\n  \n\n\n\n  \n    Waterfall y SSADM: Basados en etapas lineales, estos modelos requieren un enfoque de planificación y documentación detallada, siendo eficaces cuando las especificaciones son estables. SSADM, específicamente, añade análisis de negocio en etapas tempranas, aunque su linealidad puede provocar revisiones continuas en entornos cambiantes.\n  \n  \n    RUP (Rational Unified Process): Modelo iterativo y adaptable, es especialmente útil para proyectos complejos y de alto riesgo, aunque su flexibilidad lo hace complejo de personalizar y costoso para proyectos menores.\n  \n\n\n\n  Lean Software Development:\n\n\nInspirado en la manufactura lean de Toyota, este enfoque se centra en eliminar desperdicios, maximizar el valor al cliente y mejorar continuamente. Ideal para combinar con otros métodos (como Scrum), Lean optimiza el flujo de trabajo sin imponer una estructura rígida de desarrollo.\n\nSelección de Enfoques según Factores Clave\n\n  \n    Complejidad y requisitos: Proyectos simples pueden beneficiarse de modelos lineales, mientras que los más complejos requieren enfoques que manejen el riesgo, como Spiral o RUP.\n  \n  \n    Adaptabilidad a Cambios: Los enfoques iterativos y ágiles permiten incorporar cambios continuos en los requisitos, especialmente útiles en proyectos dinámicos.\n  \n  \n    Riesgo y Regulación: En proyectos con altos requisitos de regulación, los modelos que enfatizan documentación (como V-Model o Waterfall) o metodologías ágiles con control (como DSDM) son preferibles.\nEn conclusión, la elección del enfoque adecuado depende de factores específicos del proyecto como la complejidad, estabilidad de requisitos y participación del cliente.\n  \n\n\n\n\n\n  Ahmed, Tahir, et al. Developing Information Systems : Practical guidance for IT professionals, edited by James Cadle, BCS Learning &amp; Development Limited, 2014. ProQuest Ebook Central, http://ebookcentral.proquest.com/lib/bull-ebooks/detail.action?docID=1713962.\n\n\n\n\n",
        "url": "/intro2sd-rebeca-rodriguez-alu0101394763//chapter2"
    }
]   
```

> [!IMPORTANT]
> Si se utiliza un IDE para trabajar en el repositorio, se obtendrá un error de sintaxis en la línea 1 del fichero `/assets/src/search.json` debido a que se analizará dicho fichero como un archivo JSON puro, sin tener en cuenta el uso de Liquid. 
>
> Dado que Liquid no es JSON estándar, el IDE interpretará que la sintaxis del fichero es incorrecta. Sin embargo, al compilar el sitio web con Jekyll, este se procesará sin problemas y se generará un JSON completamente válido.
>
> Por lo tanto, este mensaje de error puede ser ignorado perfectamente.

### `search.js`
En el *script* [`/assets/src/search.js`](/assets/src/search.js) se define la clase `JekyllSearch`, que sirve para poder realizar búsquedas en el archivo `/_site/assets/src/search.json` generado.

### `fetch.js`

> [!NOTE]
> *Polyfill* es un bloque de código, normalmente JavaScript en el entorno Web, que proporciona funcionalidades modernas en navegadores antiguos que no soportan dichas funcionalidades de forma nativa.

El *script* `/assets/src/search.js` mencionado utiliza la API `fetch` de JavaScript, que sirve para realizar peticiones HTTP de forma asíncrona, de forma que se facilita la obtención de datos desde servidores.

Dado que hay navegadores antiguos que no soportan `fetch`, la definición de un *polyfill* en el fichero [`/assets/src/fetch.js`](/assets/src/fetch.js) permite que estos navegadores puedan utilizar la funcionalidad `fetch` sin tener que ser actualizados.

### `search.md`
Por último, se ha definido el fichero [`/_pages/search.md`](/_pages/search.md) mediante el que se podrá hacer uso de la nueva capacidad de búsqueda, de forma que se podrán buscar palabras clave en el sitio o incluso utilizar expresiones regulares.

Como se puede observar a continuación, los resultados se muestran en una lista que contiene los títulos de las páginas encontradas, un pequeño resumen de cada una y enlaces a las mismas. Cabe destacar que la lista de resultados se va a actualizar automáticamente a medida que el usuario vaya escribiendo.

![Muestra palabra clave](/img/muestra.png)

![Muestra regex](/img/muestra-regex.png)