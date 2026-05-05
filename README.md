# RuralSense Debug Lab - Semana 9

## 1. Propósito del taller

Este proyecto es un laboratorio práctico para aprender **pruebas y depuración web** usando herramientas reales del navegador: **consola, inspector de elementos y depurador**.

La aplicación simula un sistema comunitario llamado **RuralSense Debug Lab**, donde se registran participantes para talleres rurales. El estudiante debe explorar el proyecto, ejecutarlo, probar sus funciones, revisar la consola, inspeccionar elementos, analizar el código JavaScript y generar evidencias.

No necesitas instalar paquetes ni usar bases de datos. El proyecto funciona con:

- HTML
- CSS
- JavaScript puro
- Navegador web
- VS Code
- Extensión Live Server

---

## 2. Qué vas a practicar

Al finalizar el taller deberás poder:

1. Abrir y ejecutar un proyecto web desde VS Code.
2. Usar la consola del navegador para leer mensajes, advertencias y errores.
3. Usar el inspector para revisar HTML y CSS.
4. Usar el depurador para detener el código y analizar funciones paso a paso.
5. Probar un formulario web con datos correctos e incorrectos.
6. Identificar errores controlados y explicar por qué ocurren.
7. Documentar evidencias mediante capturas de pantalla.
8. Preparar el proyecto para subirlo a un repositorio de GitHub.

---

## 3. Estructura del proyecto

```text
ruralsense-debug-lab/
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── app.js
├── evidencias/
│   └── .gitkeep
├── .vscode/
│   ├── extensions.json
│   └── settings.json
├── .gitignore
└── README.md
```

### Descripción de carpetas y archivos

| Archivo o carpeta | Función |
|---|---|
| `index.html` | Contiene la estructura de la página web. |
| `css/styles.css` | Controla el diseño visual, colores, tarjetas, tabla y adaptación responsive. |
| `js/app.js` | Contiene la lógica del formulario, validaciones, tabla, gráfico, consola y error controlado. |
| `evidencias/` | Carpeta sugerida para guardar capturas de pantalla del taller. |
| `.vscode/` | Configuración recomendada para abrir el proyecto en VS Code. |
| `.gitignore` | Evita subir archivos innecesarios al repositorio. |
| `README.md` | Guía completa de exploración del proyecto. |

---

## 4. Cómo abrir el proyecto en VS Code

1. Descarga y descomprime el archivo `.zip`.
2. Abre VS Code.
3. Selecciona **File > Open Folder** o **Archivo > Abrir carpeta**.
4. Busca la carpeta `ruralsense-debug-lab`.
5. Ábrela completa, no abras solo un archivo individual.

Cuando el proyecto esté abierto, deberías ver las carpetas `css`, `js`, `evidencias` y el archivo `index.html`.

---

## 5. Cómo ejecutar el proyecto

### Opción recomendada: Live Server

1. Instala la extensión **Live Server** en VS Code.
2. Abre el archivo `index.html`.
3. Haz clic derecho sobre el archivo.
4. Selecciona **Open with Live Server**.
5. El navegador abrirá una dirección parecida a:

```text
http://127.0.0.1:5500/index.html
```

### Opción rápida

También puedes abrir `index.html` directamente con doble clic, pero para el taller se recomienda Live Server porque se parece más a un entorno real de desarrollo.

---

## 6. Primer recorrido por la aplicación

Al abrir la aplicación verás:

1. Un encabezado con el nombre **RuralSense Debug Lab**.
2. Tres indicadores:
   - inscritos
   - edad promedio
   - validaciones
3. Un panel del tester con botones para cargar datos, limpiar registros y generar un error controlado.
4. Un formulario de registro.
5. Una tabla de participantes.
6. Un gráfico dibujado con JavaScript.
7. Un checklist de pruebas.

Antes de modificar código, explora la página como usuario normal:

- Cambia el tema.
- Registra un participante.
- Intenta enviar el formulario vacío.
- Escribe un celular con menos de 10 dígitos.
- Carga datos de ejemplo.
- Usa el buscador.
- Presiona el botón **Generar error controlado**.

---

## 7. Uso de la consola del navegador

La consola permite ver mensajes del programa, advertencias y errores.

### Cómo abrirla

1. Abre la página en el navegador.
2. Presiona `F12`.
3. Selecciona la pestaña **Console** o **Consola**.

### Qué debes observar

Cuando la página carga, deben aparecer mensajes como:

```text
Proyecto cargado correctamente.
Sugerencia: usa breakpoints en validateForm() y addParticipant().
```

Cuando envías el formulario, el archivo `js/app.js` muestra datos en consola usando:

```javascript
console.group()
console.log()
console.table()
console.warn()
console.error()
console.info()
```

### Prueba corta

1. Abre la consola.
2. Envía el formulario vacío.
3. Observa las advertencias.
4. Escribe datos válidos.
5. Envía el formulario otra vez.
6. Observa cómo cambian los mensajes.

### Evidencia sugerida

Toma una captura donde se vea:

- La página abierta.
- La consola mostrando un mensaje o advertencia.

Guárdala en la carpeta `evidencias/` con un nombre como:

```text
evidencia_01_consola.png
```

---

## 8. Uso del inspector de elementos

El inspector permite revisar la estructura HTML y los estilos CSS aplicados.

### Cómo abrirlo

1. Clic derecho sobre el botón **Registrar participante**.
2. Selecciona **Inspeccionar**.
3. Se abrirá la pestaña **Elements** o **Elementos**.

### Qué debes revisar

Busca estos elementos:

```html
<form id="registrationForm">
<input id="fullName">
<input id="age">
<input id="phone">
<select id="workshop">
<table>
<canvas id="workshopChart">
```

Luego revisa en la parte derecha las reglas CSS aplicadas desde:

```text
css/styles.css
```

### Prueba corta

1. Inspecciona el título principal.
2. Cambia temporalmente el texto desde el inspector.
3. Cambia temporalmente el color de un botón.
4. Recarga la página.
5. Observa que los cambios temporales desaparecen.

Esto demuestra que el inspector sirve para probar visualmente, pero los cambios definitivos deben hacerse en el archivo de código.

### Evidencia sugerida

Toma una captura donde se vea el inspector abierto sobre un elemento de la página.

Guárdala como:

```text
evidencia_02_inspector.png
```

---

## 9. Uso del depurador

El depurador permite detener el código en una línea específica para revisar qué está ocurriendo.

### Cómo abrirlo

1. Presiona `F12`.
2. Abre la pestaña **Sources** o **Fuentes**.
3. Busca el archivo:

```text
js/app.js
```

### Funciones importantes para depurar

Busca estas funciones dentro de `app.js`:

```javascript
handleSubmit(event)
validateForm(data)
addParticipant(participant)
renderTable()
drawChart()
generateControlledError()
```

### Actividad con breakpoint

1. Abre `js/app.js` en la pestaña **Sources**.
2. Busca la función:

```javascript
validateForm(data)
```

3. Haz clic en el número de línea donde inicia la función para crear un breakpoint.
4. Vuelve a la página.
5. Llena el formulario.
6. Presiona **Registrar participante**.
7. El navegador pausará el código.
8. Revisa el valor de la variable `data`.
9. Avanza paso a paso con el botón **Step over**.

### Qué debes responder

Después de depurar, responde en tu cuaderno o documento de evidencias:

- ¿Qué datos llegaron a la función `validateForm`?
- ¿Qué campo generó error?
- ¿Qué condición del código detectó el error?
- ¿Qué pasó cuando corregiste los datos?

---

## 10. Error controlado del proyecto

El proyecto incluye un botón llamado:

```text
Generar error controlado
```

Este botón ejecuta la función:

```javascript
generateControlledError()
```

Dentro de esa función se intenta seleccionar un elemento que no existe:

```javascript
const missingElement = document.querySelector("#elementoQueNoExiste");
missingElement.textContent = "Esta línea genera el error controlado.";
```

El error ocurre porque `document.querySelector("#elementoQueNoExiste")` devuelve `null`. Como `null` no tiene la propiedad `textContent`, JavaScript genera un error.

El error está encerrado en un bloque:

```javascript
try {
  // código que puede fallar
} catch (error) {
  // manejo del error
}
```

Esto permite que la aplicación no se rompa por completo y que el estudiante pueda leer el error en consola.

### Tu tarea

1. Abre la consola.
2. Presiona **Generar error controlado**.
3. Lee el mensaje de error.
4. Explica con tus palabras por qué ocurrió.
5. Propón una corrección.

### Posible corrección

Una forma correcta sería validar si el elemento existe antes de modificarlo:

```javascript
const missingElement = document.querySelector("#elementoQueNoExiste");

if (missingElement) {
  missingElement.textContent = "Elemento encontrado.";
} else {
  console.warn("El elemento no existe en el HTML.");
}
```

No es obligatorio modificar el proyecto con esta corrección, pero sí debes entender por qué evita el error.

---

## 11. Pruebas sugeridas para el formulario

Realiza las siguientes pruebas y marca cuáles pasan correctamente.

| Prueba | Resultado esperado | ¿Pasó? |
|---|---|---|
| Enviar formulario vacío | Debe mostrar errores en varios campos. | Sí / No |
| Escribir nombre de 2 letras | Debe mostrar error de nombre. | Sí / No |
| Escribir edad menor a 12 | Debe mostrar error de edad. | Sí / No |
| Escribir celular de 5 dígitos | Debe mostrar error de celular. | Sí / No |
| No seleccionar taller | Debe mostrar error de taller. | Sí / No |
| Enviar datos válidos | Debe registrar el participante. | Sí / No |
| Usar el buscador | Debe filtrar por nombre o taller. | Sí / No |
| Cargar datos de ejemplo | Deben aparecer registros en la tabla. | Sí / No |
| Limpiar registros | La tabla debe quedar vacía. | Sí / No |
| Cambiar tema | Debe cambiar el aspecto visual. | Sí / No |

---

## 12. Reto de exploración avanzada

Después de completar las pruebas básicas, intenta realizar al menos dos de estos retos:

### Reto 1: Cambiar una validación

Modifica la edad mínima permitida de `12` a `14` años.

Pista: revisa esta condición en `validateForm(data)`:

```javascript
if (!Number.isInteger(data.age) || data.age < 12 || data.age > 90) {
```

### Reto 2: Agregar un nuevo taller

Agrega una nueva opción en el archivo `index.html`, por ejemplo:

```html
<option value="Robótica rural">Robótica rural</option>
```

Luego registra participantes y verifica que el gráfico también lo incluya.

### Reto 3: Cambiar el diseño de los botones

Abre `css/styles.css` y busca la clase:

```css
.btn
```

Modifica el borde, tamaño o separación. Luego revisa los cambios con el inspector.

### Reto 4: Agregar un mensaje de consola

En la función `addParticipant(participant)`, agrega:

```javascript
console.log("Nuevo participante agregado:", participant.fullName);
```

Luego registra un usuario y revisa la consola.

### Reto 5: Crear una captura final

Toma una captura donde se vea:

- Página con datos registrados.
- Consola abierta.
- Tabla actualizada.

Guárdala en `evidencias/`.

---

## 13. Qué debes entregar en Moodle

Entrega un archivo `.zip` con tu proyecto completo.

Antes de comprimirlo, verifica que incluya:

```text
index.html
css/styles.css
js/app.js
README.md
evidencias/
```

Dentro de `evidencias/`, agrega mínimo 3 capturas:

1. Página funcionando.
2. Consola con mensajes o errores.
3. Inspector o depurador abierto.

También puedes entregar un documento aparte si el docente lo solicita, pero este proyecto está diseñado para que tus evidencias puedan quedar dentro de la carpeta `evidencias/`.

---

## 14. Cómo subir el proyecto a GitHub

### Paso 1: Crear repositorio

1. Entra a GitHub.
2. Crea un nuevo repositorio.
3. Usa un nombre como:

```text
ruralsense-debug-lab
```

4. No necesitas agregar README desde GitHub porque este proyecto ya tiene uno.

### Paso 2: Inicializar Git desde VS Code

Abre la terminal de VS Code y ejecuta:

```bash
git init
git add .
git commit -m "Entrega taller Semana 9 pruebas y depuracion"
```

### Paso 3: Conectar con GitHub

GitHub te mostrará una URL parecida a:

```text
https://github.com/usuario/ruralsense-debug-lab.git
```

Ejecuta:

```bash
git branch -M main
git remote add origin URL_DEL_REPOSITORIO
git push -u origin main
```

Cambia `URL_DEL_REPOSITORIO` por la URL real de tu repositorio.

---

## 15. Preguntas cortas de cierre

Responde brevemente:

1. ¿Para qué sirve la consola del navegador?
2. ¿Qué diferencia hay entre inspeccionar un elemento y modificar el archivo CSS?
3. ¿Qué es un breakpoint?
4. ¿Qué error controlado encontraste en el proyecto?
5. ¿Qué prueba te ayudó más a entender la depuración?
6. ¿Qué mejorarías de esta aplicación?

---

## 16. Criterios de evaluación sugeridos

| Criterio | Valor |
|---|---:|
| Ejecuta correctamente el proyecto en VS Code o navegador | 20% |
| Usa consola, inspector o depurador con evidencia | 25% |
| Realiza pruebas del formulario y registra resultados | 20% |
| Explica el error controlado y su posible solución | 20% |
| Entrega organizada con capturas o repositorio | 15% |
| **Total** | **100%** |

---

## 17. Recomendación final

No te limites a mirar si la página “se ve bonita”. Un desarrollador prueba, observa, compara, corrige y vuelve a probar.

Este taller busca que aprendas a pensar como tester y desarrollador:

```text
Ejecutar → Observar → Detectar → Corregir → Probar otra vez → Documentar
```
