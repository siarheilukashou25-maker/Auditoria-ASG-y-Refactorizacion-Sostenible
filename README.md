
## Fase 1: Inventario y Dimensión Ambiental (A)

### Medición inicial

Aunque todavía no disponemos de una página web funcional, ya podemos plantear una estrategia para obtener una buena puntuación en herramientas como Website Carbon Calculator.

![Foto de la nota](https://i.ibb.co/wNrwVtVw/2026-05-19-11-08-38.png)

Los factores que más afectan a esta métrica son principalmente el peso total de la página y la cantidad de solicitudes de red. Por ello, nos enfocaremos en optimizar al máximo el rendimiento y reducir el consumo innecesario de recursos.

| Qué | Cómo afecta |
|--|--|
| Webfonts | Entre 300 y 800 KB, o incluso más si se utilizan fuentes innecesarias |
| Imágenes | Representan aproximadamente entre el 70 % y el 90 % del peso total de la página |
| Vídeos | Generan un impacto muy elevado en consumo de datos y carga |
| Analítica y trackers | Pueden realizar múltiples solicitudes de red innecesarias |

### Medidas planteadas

- No se utilizarán vídeos en la página web debido a su elevado impacto energético y de transferencia de datos.
- Para la analítica, se empleará únicamente una solución *self-hosted* (autoalojada), evitando servicios externos y trackers innecesarios.
- Las imágenes se optimizarán utilizando el formatos `avif`, `svg` `.webp` y técnicas de *lazy-loading*.
- No se utilizarán fuentes externas, como Google Fonts. En su lugar, se emplearán fuentes del sistema para reducir las solicitudes externas y mejorar el rendimiento.

### ¿Las páginas web sufren de “inflación de software”?

En cierta medida, sí. Sin embargo, depende principalmente de la experiencia y las prácticas de los profesionales que desarrollan el sitio web.

No es lo mismo una página creada por un desarrollador principiante o mediante *vibe-coding* (desarrollo excesivamente dependiente de IA y generación automática de código) que un proyecto desarrollado por profesionales con experiencia en rendimiento, sostenibilidad y buenas prácticas DevOps.

En muchos casos, una mala arquitectura, dependencias innecesarias y frameworks sobredimensionados provocan aplicaciones más pesadas y menos sostenibles. Por el contrario, los proyectos desarrollados por profesionales especializados suelen ser más eficientes, aunque también impliquen un mayor coste de desarrollo.

---

## Fase 2: Dimensión Social y Equidad (S)

Para garantizar que la página web sea lo más accesible posible, se aplicarán buenas prácticas de accesibilidad y usabilidad:

- Todas las imágenes incluirán atributos `alt` con descripciones adecuadas.
- El texto mantendrá un contraste suficiente para facilitar la lectura.
- Los formularios (por ejemplo, login y contraseña) tendrán etiquetas `label` correctamente asociadas.
- Todos los botones serán accesibles mediante teclado, incluyendo estados `focus` visibles y texto descriptivo.
- Se utilizará HTML semántico adecuado (`header`, `main`, `footer`, `nav`, `h1`, etc.) en lugar de depender exclusivamente de `div`.

Estas medidas no solo mejoran la accesibilidad para personas con discapacidades, sino que también contribuyen a una mejor experiencia de usuario y a un desarrollo web más sostenible y profesional.


## Fase 3: Dimensión de Gobernanza y Ética (G)

Actualmente no está previsto monetizar la página web de forma directa. Por este motivo, en la fase inicial del proyecto no será necesario utilizar cookies de analítica, marketing o seguimiento. No obstante, se contempla la posibilidad de incorporar determinadas funcionalidades en el futuro, por lo que la gestión del consentimiento deberá diseñarse desde el inicio siguiendo criterios éticos y transparentes.

Con el objetivo de garantizar una buena experiencia de usuario y un tratamiento responsable de los datos, se aplicarán las siguientes medidas:

-   El banner de consentimiento mostrará los botones **“Aceptar”** y **“Rechazar”** con el mismo tamaño, diseño y nivel de visibilidad, evitando prácticas engañosas o manipulativas.
-   Se explicará de forma clara y comprensible qué tipos de cookies se utilizan y con qué finalidad.
-   Las cookies de analítica o marketing no se activarán antes de que el usuario otorgue su consentimiento explícito.
-   El usuario podrá modificar su decisión en cualquier momento desde la configuración de privacidad de la página.

En relación con el formulario de comentarios, se aplicará el principio de minimización de datos. Únicamente se solicitarán los datos estrictamente necesarios para la comunicación:

-   Nombre
-   Correo electrónico de contacto
-   Comentario

De esta manera se reduce la recopilación innecesaria de información personal y se mejora la privacidad del usuario.

----------

# Fase 4: Propuesta de Refactorización (Green Coding)

## Optimización de activos digitales

Con el objetivo de mejorar la eficiencia energética y reducir el consumo de recursos, se utilizarán distintos formatos de imagen según el tipo de contenido:

### Formato AVIF

Se utilizará para:

-   Fotografías
-   Fondos
-   Imágenes de gran tamaño

Este formato ofrece una compresión superior y reduce significativamente el peso de los archivos sin perder calidad visual.

### Formato WebP

Se utilizará como:

-   Fallback para navegadores sin soporte AVIF
-   Compatibilidad con navegadores antiguos
-   Imágenes medianas e iconografía ligera

### Formato SVG

Se utilizará para:

-   Logos
-   Iconos
-   Ilustraciones simples
-   Elementos vectoriales y botones

El uso de SVG permite mantener una alta calidad visual con un tamaño de archivo mínimo.

Además, se implementará la técnica de **Lazy Loading**, permitiendo que las imágenes se carguen progresivamente a medida que el usuario navega por la página. Esto reduce el consumo inicial de recursos y mejora los tiempos de carga.

----------

## Base de datos

Para la gestión de datos se utilizará **PostgreSQL**.

Aunque una solución como **SQLite** podría ser válida para proyectos pequeños, PostgreSQL resulta más adecuado debido a la complejidad prevista de la base de datos y a sus ventajas en:

-   Eficiencia
-   Flexibilidad
-   Escalabilidad
-   Código abierto
-   Compatibilidad con despliegues modernos de tamaño pequeño y mediano

----------

## Infraestructura y hosting

### Hosting web

Se utilizará [Cloudflare Pages](https://pages.cloudflare.com?utm_source=chatgpt.com) como plataforma de despliegue del frontend debido a sus ventajas en rendimiento, distribución global y eficiencia energética.

### Servidor de base de datos y API

Para el backend y la base de datos se utilizará un VPS pequeño de [Hetzner](https://www.hetzner.com?utm_source=chatgpt.com), priorizando una infraestructura ligera y eficiente en consumo de recursos.

----------

## Reducción de peticiones y dependencias externas

Con el objetivo de minimizar las solicitudes externas y mejorar la sostenibilidad del proyecto:

-   No se utilizarán herramientas de analítica ni sistemas de seguimiento.
-   Se emplearán fuentes tipográficas del sistema en lugar de servicios externos.
-   Se evitarán frameworks pesados como Bootstrap u otros similares.
-   El diseño se desarrollará utilizando CSS nativo, reduciendo dependencias y tamaño de descarga.

Estas decisiones permiten disminuir el consumo de ancho de banda, mejorar el rendimiento y reducir la huella energética de la aplicación.

----------

## Reflexión sobre la Paradoja de Jevons

La Paradoja de Jevons establece que:

> “Cuando algo se vuelve más eficiente, muchas veces termina consumiéndose más.”

Aplicado al desarrollo web, esto significa que una página optimizada puede terminar generando un mayor consumo total si atrae un volumen masivo de usuarios o fomenta un uso excesivo de la plataforma.

Desde una perspectiva de sostenibilidad digital y ética, no se implementarán prácticas diseñadas para maximizar artificialmente el tiempo de permanencia del usuario, tales como:

-   Scroll infinito
-   Notificaciones agresivas
-   Patrones oscuros (“dark patterns”)
-   Técnicas de adicción digital

Sin embargo, desde un enfoque puramente empresarial, este tipo de estrategias suele utilizarse para aumentar métricas de permanencia, ingresos publicitarios y volumen de ventas. Por ejemplo, durante el proceso de compra podrían mostrarse promociones adicionales, recomendaciones personalizadas o productos relacionados para incentivar un mayor consumo.

Precisamente por este motivo, el enfoque Green Coding busca equilibrar los objetivos comerciales con principios éticos y sostenibles. En lugar de priorizar únicamente el beneficio económico, se propone desarrollar soluciones responsables que respeten el tiempo, la privacidad y la experiencia del usuario.

Como parte de esta filosofía, cualquier futura incorporación de sistemas de analítica, seguimiento o funcionalidades potencialmente invasivas debería evaluarse cuidadosamente desde criterios de sostenibilidad y transparencia.
