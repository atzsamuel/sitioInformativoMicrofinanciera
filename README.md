# sitioInformativoMicrofinanciera

Proyecto de sitio informativo para una microfinanciera (Banco De Mi Gente). Esta pequeña web está pensada
para mostrar información de microcréditos, requisitos para aplicar y una sección de preguntas frecuentes.

## Estructura del proyecto

- `index.html` — Página principal con la maquetación y las secciones: header, inicio, requisitos, preguntas frecuentes y enlaces a WhatsApp.
- `styles.css` — Estilos principales para la presentación (header fijo, tarjetas, sección de requisitos y FAQ).
- `script.js` — JavaScript que controla la interacción: desplegado de las preguntas frecuentes y menú móvil.
- `README.md` — Documentación del proyecto (este archivo).

## Descripción por secciones (basado en `index.html`)

- Header
	- Logo: texto "Banco De Mi Gente".
	- Navegación: enlaces a `#inicio`, `#requisitos` y `#preguntasfrecuentes`.
	- Botón de menú móvil que llama a `toggleMenu()` para abrir/cerrar el panel móvil.

- Sección "Inicio" (`#inicio`)
	- Título principal y párrafo descriptivo.
	- Botón que enlaza a WhatsApp para solicitar microcrédito.
	- Contenedor de tarjetas (`.cards-container`) con 3 tarjetas que muestran ventajas (cuotas accesibles, proceso rápido, transparencia).

- Sección "Requisitos" (`#requisitos`)
	- Listado de documentos requeridos: DPI, recibo de luz, escritura o fiador y comprobante de ingresos opcional.
	- Botón central para enviar documentos por WhatsApp.

- Sección "Preguntas Frecuentes" (`#preguntasfrecuentes`)
	- Varias preguntas con botón expansible; las respuestas están ocultas por defecto y se muestran al hacer clic.

- Elementos adicionales
	- Menú móvil (`.mobile-menu`) con enlaces y botón de cierre.
	- Botón flotante de WhatsApp (`.whatsapp-float`) para contacto rápido.

## Comportamiento y scripts (`script.js`)

- Funcionalidad principal:
	- Toggle de preguntas frecuentes: se añaden listeners a los botones `.faq-question` para alternar la clase `active` en su elemento padre y así mostrar/ocultar la respuesta.
	- `toggleMenu()` alterna la clase `active` del menú móvil para abrir/cerrar el panel.

- Observaciones y recomendaciones:
	- Actualmente `script.js` contiene bloques `DOMContentLoaded` repetidos (duplicados). Recomiendo consolidarlos en uno solo para evitar registros redundantes.
	- Hay variables `width` y `height` que almacenan `window.innerWidth`/`innerHeight` pero no se usan — pueden eliminarse o usarse para lógica responsiva.

## Estilos principales (`styles.css`)

- Describe tipografías, paleta (tonos de verde), layout del header fijo, estilos de tarjetas y diseño de FAQ.
- Puntos a revisar:
	- Hay algunas propiedades con pequeñas inconsistencias (por ejemplo `padding: 25 px;` tiene un espacio extra y `font-size: 15PX` usa mayúsculas). Normalizar esos valores mejorará compatibilidad.
	- Revisar `margin-top` repetido en `main` y posibles reglas duplicadas.

## Cómo ver el proyecto localmente

1. Clona o descarga el repositorio y abre la carpeta del proyecto.
2. Para una vista rápida, abre `index.html` en tu navegador (doble clic).
3. Si prefieres servirlo por un servidor local (recomendado para evitar problemas con algunas APIs), con Python 3 puedes ejecutar en PowerShell:

```powershell
# desde la carpeta del proyecto
python -m http.server 8000
# luego abre http://localhost:8000 en tu navegador
```

## Accesibilidad y buenas prácticas

- Asegurarse de que los botones tengan atributos ARIA cuando sea necesario (por ejemplo, `aria-expanded` en las preguntas FAQ).
- Añadir texto alternativo y roles semánticos si se incluyen imágenes o componentes interactivos adicionales.

## Tareas pendientes / mejoras sugeridas

1. Consolidar los bloques `DOMContentLoaded` duplicados en `script.js`.
2. Corregir pequeños errores de CSS (`25 px` → `25px`, `15PX` → `15px`).
3. Mejorar la experiencia móvil: ajustar `nav` y espaciados para pantallas pequeñas; probar el menú móvil en distintos anchos.
4. Añadir pruebas básicas (si procede) o una comprobación rápida de lint para CSS/JS.

## Cómo contribuir

- Haz un fork, crea una rama con la mejora (`feature/mi-mejora`), realiza commits claros y abre un pull request.
- Puedes usar Issues para reportar bugs o proponer nuevas funcionalidades.

## Licencia

Indica aquí la licencia del proyecto (por ejemplo MIT) o añade una sección `LICENSE` si corresponde.

## Contacto

Para dudas o soporte, contactar al propietario del repositorio.

---

Si quieres, puedo:

- Aplicar las correcciones automáticas sugeridas en `script.js` y `styles.css` (con cambios mínimos y seguros).
- Añadir comprobaciones de lint básicas (eslint/prettier para JS o stylelint para CSS).

Indica qué prefieres que haga a continuación.
