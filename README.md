# OVA: Fundamentos de Programación en Pseudocódigo

Objeto Virtual de Aprendizaje (OVA) sobre lógica y resolución de problemas, exportado para la web desde Articulate Rise. Incluye explicaciones, ejemplos, actividades interactivas y evaluación final.

## ¿Se puede ejecutar tal como está?

**Sí. El repositorio contiene el aplicativo web listo para servir.** No requiere compilar código, instalar paquetes con `npm` o `pip`, configurar una base de datos ni iniciar un backend propio.

Para usarlo localmente, sigue los pasos de este documento: descarga todos los archivos y abre el curso mediante un servidor HTTP local. Este servidor únicamente entrega los archivos al navegador; la aplicación se ejecuta en el navegador.

**No se incluye `requirements.txt` porque no existen dependencias de Python que instalar.** Python es una opción para iniciar el servidor local y su módulo `http.server` viene incluido en la biblioteca estándar. Tampoco se necesita `package.json`, `npm install` ni `npm run dev` para esta exportación.

## Requisitos

- Un navegador con JavaScript habilitado, como Chrome, Edge o Firefox.
- Todos los archivos del repositorio, conservando sus nombres y carpetas.
- Para el método local explicado aquí: **Python 3**. Puedes obtenerlo desde [python.org](https://www.python.org/downloads/).
- Git solamente si eliges descargar mediante `git clone`; con la descarga ZIP no es necesario.

La descarga inicial necesita conexión a Internet. Los recursos principales del curso están incluidos en el repositorio; los enlaces o contenidos externos, si se utilizan, requieren conexión a sus respectivos servicios.

## 1. Descargar el aplicativo

Elige **una** de las siguientes alternativas.

### Alternativa A: descargar ZIP, sin usar Git

1. Abre [el repositorio en GitHub](https://github.com/JulianOrtiz952/ova-multimedia).
2. Selecciona **Code → Download ZIP**.
3. Extrae el ZIP completo en una carpeta de tu equipo. No ejecutes el curso desde dentro del archivo comprimido.
4. Entra en la carpeta extraída, normalmente `ova-multimedia-main`.
5. Confirma que ves `index.html`, `runtime-data.js`, `assets` y `lib`.

### Alternativa B: clonar con Git

Abre una terminal en la ubicación donde quieras guardar el aplicativo y ejecuta:

```powershell
git clone https://github.com/JulianOrtiz952/ova-multimedia.git
cd ova-multimedia
```

## 2. Abrir una terminal en la carpeta correcta

La terminal debe estar ubicada **en la carpeta que contiene `index.html`**.

En Windows puedes abrir esa carpeta en el Explorador de archivos, escribir `powershell` en la barra de direcciones y presionar Enter.

Para comprobar la ubicación en PowerShell:

```powershell
Get-ChildItem
```

Debes ver, como mínimo:

```text
index.html
runtime-data.js
assets/
lib/
```

Si estás usando la copia original de este proyecto en el equipo donde se preparó, la carpeta es `curso-web/content`. Si descargaste o clonaste este repositorio, los archivos ya están en su raíz: no necesitas crear esa carpeta adicional.

## 3. Iniciar el servidor local

En Windows, ejecuta:

```powershell
py -3 -m http.server 8765 --bind 127.0.0.1
```

Si Windows no reconoce `py`, comprueba que `python --version` muestra Python 3 y utiliza:

```powershell
python -m http.server 8765 --bind 127.0.0.1
```

En macOS o Linux, el comando habitual es:

```bash
python3 -m http.server 8765 --bind 127.0.0.1
```

**Ejecuta solo uno de esos comandos.** Cuando el servidor esté activo, la terminal mostrará un mensaje parecido a `Serving HTTP on 127.0.0.1 port 8765`. Déjala abierta mientras uses el OVA. Los mensajes `GET` que aparezcan al navegar son normales.

## 4. Abrir y utilizar el OVA

Abre esta dirección en el navegador:

**[http://127.0.0.1:8765/](http://127.0.0.1:8765/)**

1. Espera a que cargue la lección **Bienvenida y Diagnóstico Inicial**.
2. Lee las instrucciones y desplázate hacia abajo para ver las actividades.
3. Usa el botón del menú para abrir la tabla de contenidos y acceder a las lecciones.
4. Pulsa **COMENZAR** en los recorridos guiados, abre las secciones desplegables y voltea las tarjetas para explorar el material.
5. En las preguntas, selecciona tu respuesta y pulsa **ENVIAR** cuando corresponda.
6. Utiliza los controles para continuar y consulta la evaluación final al terminar el recorrido.

El curso contiene ocho lecciones:

1. Bienvenida y Diagnóstico Inicial.
2. Algoritmos y Pseudocódigo: Conceptos y Representación Visual.
3. Variables, Constantes y Tipos de Datos en Pseudocódigo.
4. Operadores y Entrada/Salida: Manipulación de Datos en Pseudocódigo.
5. Estructuras de Control: Secuencias, Decisiones y Ciclos.
6. Modularidad: Funciones, Procedimientos y Resolución de Problemas.
7. Taller Integrador y Evaluación Final.
8. Evaluación final.

### Cerrar y volver a abrir

- Para detener el servidor, vuelve a la terminal y presiona **Ctrl+C**.
- Para usar el curso otro día, abre la terminal en la misma carpeta, ejecuta otra vez el comando del paso 3 y visita la misma dirección.
- Esta exportación no incluye un sistema propio de cuentas ni una base de datos central de estudiantes. No debe utilizarse como registro institucional de notas o como garantía de conservación del progreso entre dispositivos o sesiones.

## Problemas frecuentes

### `py`, `python` o `python3` no se reconoce

Instala Python 3 y abre una terminal nueva. En Windows, si el instalador ofrece **Add Python to PATH**, activa esa opción. Vuelve a probar uno de los comandos del paso 3. No necesitas ejecutar `pip install`.

### El puerto está ocupado o aparece otro sitio

Detén únicamente el servidor que hayas iniciado para este curso con **Ctrl+C** y elige otro puerto, por ejemplo:

```powershell
python -m http.server 8766 --bind 127.0.0.1
```

Luego visita **http://127.0.0.1:8766/**. El número de la dirección debe coincidir con el del comando. No es necesario cerrar otros aplicativos que usen un puerto distinto.

### El navegador muestra una lista de archivos o un error 404

Comprueba que iniciaste el servidor en la carpeta que contiene `index.html`. Si lo iniciaste en la carpeta superior, detén el servidor, entra en la carpeta correcta y vuelve a iniciarlo.

### La página queda en blanco, faltan recursos o una actividad no carga

1. Comprueba que descargaste y extrajiste el repositorio completo.
2. Verifica que `assets`, `lib` y `runtime-data.js` permanecen junto a `index.html`.
3. Abre la URL HTTP del paso 4. El procedimiento documentado y verificado utiliza un servidor local; abrir `index.html` con doble clic no es el método de comprobación utilizado.
4. Confirma que el servidor sigue activo y que JavaScript está habilitado.
5. Recarga la página con **Ctrl+F5**. Si el problema continúa, abre las herramientas del navegador con **F12** y revisa la consola y la pestaña de red para identificar el archivo que falla.

### ¿Por qué no abre como sitio al visitar el repositorio en GitHub?

La página del repositorio permite consultar y descargar los archivos. Subirlos con Git no configura por sí solo una publicación del sitio. Para compartir el OVA mediante una URL pública se necesita configurar un alojamiento web estático que sirva `index.html` y todas las carpetas del proyecto.

El servidor de este documento escucha en `127.0.0.1`: sirve para acceder desde el mismo equipo. Esa dirección no es un enlace público para enviar a otros estudiantes.

## Estructura del proyecto

```text
ova-multimedia/
├── index.html        # Entrada del aplicativo
├── runtime-data.js   # Contenido y configuración exportados del curso
├── assets/           # Recursos gráficos incluidos
├── lib/              # JavaScript, estilos, fuentes y componentes del reproductor
└── README.md         # Instrucciones de uso
```

Esta es una exportación lista para ejecutar. Los archivos JavaScript están empaquetados; para cambios pedagógicos o estructurales del curso, el flujo recomendado es editar el proyecto original en Articulate Rise, exportarlo de nuevo para web y actualizar estos archivos.

## Verificación realizada

Se probó esta copia con **Python 3.12** mediante `python -m http.server 8765 --bind 127.0.0.1` y un navegador basado en Chromium. Se comprobó la carga de la primera lección, el avance de su carrusel y la navegación desde el menú hacia la segunda lección, sin errores ni advertencias de consola durante esas comprobaciones.

Estas comprobaciones confirman el inicio y una parte de la interacción. No equivalen a una revisión exhaustiva de todas las actividades, de la evaluación final ni de todos los navegadores.
