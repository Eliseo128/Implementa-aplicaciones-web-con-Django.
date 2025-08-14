¡Perfecto! A continuación, te presento una **planeación didáctica completa** para el módulo:

---

# 📘 **SM 2 UII: Introducción a Django (Framework Web con Python)**  
**Duración:** 25 horas (13 sesiones de 2 horas + 1 hora de evaluación)  
**Nivel:** Principiante  
**Dirigido a:** Estudiantes de preparatoria o nivel medio técnico  
**Prerrequisito:** Conocimientos básicos de Python (variables, funciones, condicionales)

---

## ✅ **Objetivo General del Módulo**
Que los estudiantes comprendan el funcionamiento básico de una página web dinámica y desarrollen las habilidades necesarias para crear una aplicación web funcional utilizando el framework Django, mediante un enfoque práctico, progresivo y centrado en el aprendizaje activo.

---

## 🎯 **Objetivos Específicos**
Al finalizar este módulo, el estudiante será capaz de:
1. Explicar la diferencia entre páginas estáticas y dinámicas con ejemplos del entorno escolar.
2. Instalar Django y crear un entorno de desarrollo web funcional.
3. Crear un proyecto y una aplicación en Django siguiendo la estructura recomendada.
4. Configurar vistas y URLs para mostrar contenido en el navegador.
5. Utilizar plantillas (templates) para generar páginas web dinámicas con datos variables.
6. Integrar los componentes básicos de Django (proyecto, app, vistas, URLs, templates) en un mini-proyecto funcional.

---

## 🗓️ **Distribución de las 25 Horas (13 sesiones de 2 horas + 1 hora de evaluación)**

| Sesión | Tema | Horas |
|--------|------|-------|
| 1 | ¿Qué es una página web dinámica? | 2 |
| 2 | ¿Qué es Django? Ventajas y casos de uso | 2 |
| 3 | Instalación de Django y entorno de trabajo | 2 |
| 4 | Creación de tu primer proyecto en Django | 2 |
| 5 | Estructura de carpetas y archivos en Django | 2 |
| 6 | Ejecutar el servidor y ver tu sitio web | 2 |
| 7 | Crear tu primera aplicación (app) en Django | 2 |
| 8 | Vistas: mostrar mensajes en pantalla | 2 |
| 9 | URLs: conectar rutas con funciones | 2 |
| 10 | Plantillas (Templates): crear páginas HTML | 2 |
| 11 | Usar variables en plantillas | 2 |
| 12 | Integración: proyecto funcional (página personal) | 2 |
| 13 | Presentación del proyecto y revisión | 2 |
| – | Evaluación final (escrita + práctica) | 1 |

---

## 🧩 **Planeación Detallada por Sesión**

---

### **Sesión 1: ¿Qué es una página web dinámica?**

**Apertura (30 min)**  
- Dinámica: "¿Qué sitios web usas todos los días?" (lluvia de ideas)  
- Mostrar ejemplos: Facebook (cambia), Wikipedia (estática)  
- Pregunta guía: *¿Por qué Instagram muestra cosas distintas cada vez que entras?*

**Desarrollo (60 min)**  
- Explicación con dibujos:  
  - Página estática: como un cartel fijo  
  - Página dinámica: como un periódico que se actualiza  
- Ejemplos reales: blogs, redes sociales, tiendas en línea  
- Características: contenido cambia, interactúa con el usuario, usa base de datos

**Cierre (30 min)**  
- Actividad: en parejas, identificar 3 páginas estáticas y 3 dinámicas  
- Compartir resultados y justificar  
- Tarea: traer idea de una página que les gustaría crear

---

### **Sesión 2: ¿Qué es Django?**

**Apertura (30 min)**  
- Video corto (3 min): "Empresas que usan Django" (Instagram, Pinterest, Disqus)  
- Pregunta: *¿Por qué usar Python para hacer páginas web?*

**Desarrollo (60 min)**  
- ¿Qué es un framework? Analogía: "kit de herramientas para construir casas"  
- Características de Django:  
  - Todo incluido (baterías incluidas)  
  - Seguro, rápido, fácil de aprender  
  - Comunidad grande y documentación excelente  
- Casos de uso: blogs, sistemas escolares, tiendas

**Cierre (30 min)**  
- Actividad: mapa mental "¿Por qué elegir Django?"  
- Compartir en grupo

---

### **Sesión 3: Instalación de Django**

**Apertura (30 min)**  
- Demo: mostrar consola y comando `pip install django`  
- Pregunta: *¿Qué es un administrador de paquetes?*

**Desarrollo (60 min)**  
- Paso a paso:  
  1. Verificar Python: `python --version`  
  2. Instalar Django: `pip install django`  
  3. Verificar instalación: `django-admin --version`  
- Solución de errores comunes (permisos, PATH)

**Cierre (30 min)**  
- Ejercicio: cada estudiante instala Django en su equipo  
- Captura de pantalla como evidencia  
- Apoyo entre pares

---

### **Sesión 4: Crear tu primer proyecto en Django**

**Apertura (30 min)**  
- Mostrar estructura final del proyecto (carpetas)  
- Pregunta: *¿Qué significa "proyecto" en Django?*

**Desarrollo (60 min)**  
- Comando: `django-admin startproject mi_sitio`  
- Explicación del nombre del proyecto  
- Navegación en carpetas (usar `cd`)

**Cierre (30 min)**  
- Ejercicio: crear un proyecto llamado `blog_escolar`  
- Verificar que se generó la carpeta y archivos  
- Compartir en grupo si tuvieron errores

---

### **Sesión 5: Estructura de carpetas y archivos en Django**

**Apertura (30 min)**  
- Juego: "¿Qué archivo soy?" (tarjetas con nombres: `settings.py`, `urls.py`, etc.)

**Desarrollo (60 min)**  
- Análisis de archivos clave:  
  - `manage.py`: herramienta principal  
  - `settings.py`: configuración (idioma, zona horaria)  
  - `urls.py`: rutas del sitio  
  - Carpeta del proyecto: `mi_sitio/`

**Cierre (30 min)**  
- Actividad: etiquetar un diagrama de carpetas  
- Modificar `settings.py`: cambiar idioma a `'es-mx'` y zona a `'America/Mexico_City'`

---

### **Sesión 6: Ejecutar el servidor de desarrollo**

**Apertura (30 min)**  
- Pregunta: *¿Qué es un servidor?* Analogía: "mesero que trae páginas web"

**Desarrollo (60 min)**  
- Comando: `python manage.py runserver`  
- Acceder a `http://localhost:8000`  
- Detener el servidor (Ctrl + C)  
- Cambiar puerto si es necesario

**Cierre (30 min)**  
- Ejercicio: iniciar el servidor y tomar captura de la página de bienvenida  
- Modificar mensaje de bienvenida (opcional: editar `wsgi.py` para ver error, luego corregir)

---

### **Sesión 7: Crear tu primera aplicación (app) en Django**

**Apertura (30 min)**  
- Analogy: proyecto = escuela, app = biblioteca, app = cafetería  
- Pregunta: *¿Para qué sirve una "app" en Django?*

**Desarrollo (60 min)**  
- Comando: `python manage.py startapp pagina`  
- Estructura de la app: `views.py`, `models.py`, `apps.py`  
- Registrar app en `settings.py` → `INSTALLED_APPS`

**Cierre (30 min)**  
- Ejercicio: crear app llamada `inicio`  
- Registrarla y verificar que no hay errores al iniciar el servidor

---

### **Sesión 8: Vistas (Views): mostrar un mensaje**

**Apertura (30 min)**  
- Pregunta: *¿Dónde se escribe el contenido que ves en pantalla?*

**Desarrollo (60 min)**  
- Editar `views.py`:  
  ```python
  from django.http import HttpResponse
  def saludo(request):
      return HttpResponse("¡Hola desde Django!")
  ```
- Probar vista temporalmente con `urls.py` del proyecto

**Cierre (30 min)**  
- Ejercicio: crear una vista `acerca_de` que muestre "Este sitio lo hice yo"  
- Acceder desde navegador

---

### **Sesión 9: URLs: conectar rutas con funciones**

**Apertura (30 min)**  
- Juego: "Conecta la URL con su vista" (tarjetas desordenadas)

**Desarrollo (60 min)**  
- Mover `urls.py` a la app (`inicio/urls.py`)  
- Configurar rutas:  
  ```python
  path('inicio/', views.saludo),
  path('acerca/', views.acerca_de),
  ```
- Incluir app en `urls.py` del proyecto: `path('', include('inicio.urls'))`

**Cierre (30 min)**  
- Ejercicio: crear ruta `/hola` que muestre un saludo personalizado  
- Probar en `localhost:8000/hola`

---

### **Sesión 10: Plantillas (Templates): crear páginas HTML**

**Apertura (30 min)**  
- Mostrar una página HTML bonita vs. solo texto  
- Pregunta: *¿Cómo hago que mi sitio se vea bien?*

**Desarrollo (60 min)**  
- Crear carpeta `templates` dentro de la app  
- Crear `index.html`:  
  ```html
  <h1>Bienvenido a mi sitio</h1>
  <p>Hecho con Django</p>
  ```
- Configurar `settings.py` para encontrar templates  
- Modificar vista para usar `render()`

**Cierre (30 min)**  
- Ejercicio: mostrar `index.html` al entrar a la raíz (`/`)  
- Agregar una imagen con `<img>` (usar URL externa)

---

### **Sesión 11: Usar variables en plantillas**

**Apertura (30 min)**  
- Pregunta: *¿Cómo pongo mi nombre en la página sin editar el HTML?*

**Desarrollo (60 min)**  
- Enviar variables desde la vista:  
  ```python
  context = {'nombre': 'Ana', 'edad': 17}
  return render(request, 'index.html', context)
  ```
- Usar en HTML: `{{ nombre }} tiene {{ edad }} años`

**Cierre (30 min)**  
- Ejercicio: crear una vista que muestre una lista de materias escolares  
- Usar `{{ }}` y `for` en la plantilla

---

### **Sesión 12: Proyecto Integrador – Mi Página Personal**

**Apertura (30 min)**  
- Revisión de objetivos del proyecto:  
  - Mostrar información personal  
  - Usar vistas, URLs, templates y variables  
- Entrega de rúbrica básica

**Desarrollo (90 min)**  
- Actividad: cada estudiante crea:  
  - Vista para "Inicio"  
  - Vista para "Acerca de mí"  
  - Plantillas con estilos básicos (colores, títulos)  
  - Variables con nombre, edad, pasatiempos

**Cierre (0 min)**  
*(Continúa en sesión 13)*

---

### **Sesión 13: Presentación del Proyecto y Revisión**

**Apertura (30 min)**  
- Preparar presentación: ¿qué hace tu página? ¿qué fue lo más difícil?

**Desarrollo (60 min)**  
- Presentaciones individuales o en parejas (3 min cada uno)  
- Demo en vivo del sitio en su computadora

**Cierre (30 min)**  
- Retroalimentación entre pares (ficha sencilla: ✅ Lo que me gustó, 💡 Sugerencia)  
- Entrega de constancia simbólica  
- Encuesta de satisfacción

---

### **Evaluación Final (1 hora)**  
- **Práctica (60%)**: funcionamiento del proyecto (vistas, URLs, templates, variables)  
- **Escrita (40%)**: 10 preguntas cortas sobre conceptos (ej: ¿para qué sirve `settings.py`?)  
- Rúbrica de evaluación proporcionada con anticipación

---

## 🧰 **Recursos Necesarios**
- Computadoras con Python 3.8+ y acceso a internet
- Editor de código: VS Code, Thonny o IDLE
- Proyector y pizarrón digital
- Guías de trabajo por sesión (PDF o impresas)
- Repositorio en GitHub Classroom (opcional)

---

## 🌱 **Estrategias Pedagógicas**
- Aprendizaje basado en proyectos (ABP)
- Aprendizaje entre pares (pair programming ocasional)
- Aula invertida parcial (videos cortos antes de clase)
- Gamificación: insignias por logros (ej: "Instalador Django", "Maestro de URLs")

---

Este plan está diseñado para que los estudiantes **aprendan haciendo**, construyendo desde el primer día y consolidando sus conocimientos en un proyecto significativo y personal.

¿Te gustaría que te genere las **guías de trabajo semanales** o un **modelo de rúbrica de evaluación** para el proyecto final?
