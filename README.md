# Auditoria-ASG-y-Refactorizacion-Sostenible


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
- Las imágenes se optimizarán utilizando el formato `.webp` y técnicas de *lazy-loading*.
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
