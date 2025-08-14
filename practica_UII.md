¡Claro! A continuación, te presento una **práctica paso a paso** para la **Unidad II: Introducción a Django**, con un proyecto funcional llamado **`misitio`** y una aplicación **`estudiante`** que incluye un modelo con 3 campos, vistas, URLs, plantillas y todo lo necesario para que sea **100% funcional**.

Esta práctica es ideal para estudiantes de preparatoria o nivel principiante y puede realizarse en **4-5 sesiones de 2 horas**.

---

# 📘 **Práctica UII: Proyecto "misitio" con aplicación "estudiante"**

> **Objetivo:** Crear un sitio web con Django que muestre una lista de estudiantes registrados, usando modelos, vistas, URLs y plantillas.

---

## ✅ **Requisitos Previos**
- Python 3.8 o superior instalado
- Django instalado (`pip install django`)
- Editor de código (VS Code, Thonny, etc.)
- Conocimientos básicos: variables, funciones, HTML simple

---

## 🗂️ **Estructura Final del Proyecto**

```
misitio/
│
├── manage.py
│
├── misitio/                     # Carpeta del proyecto
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
└── estudiante/                  # Aplicación
    ├── __init__.py
    ├── admin.py
    ├── apps.py
    ├── models.py
    ├── views.py
    ├── urls.py                  # (crear este archivo)
    └── templates/
        └── estudiante/
            ├── index.html
            └── detalle.html
```

---

## 🛠️ **Paso 1: Crear el Proyecto "misitio"**

### 1. Abre la terminal (consola)
```bash
django-admin startproject misitio
```

### 2. Entra a la carpeta
```bash
cd misitio
```

✅ **Resultado:** Tienes un proyecto Django llamado `misitio`.

---

## 🔧 **Paso 2: Crear la Aplicación "estudiante"**

### 1. Crea la app
```bash
python manage.py startapp estudiante
```

### 2. Registra la app en `misitio/settings.py`
Busca `INSTALLED_APPS` y agrega `'estudiante'`:

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'estudiante',  # ← AQUÍ
]
```

---

## 📄 **Paso 3: Crear el Modelo (3 campos)**

Abre el archivo: `estudiante/models.py`

```python
from django.db import models

class Estudiante(models.Model):
    nombre = models.CharField(max_length=100)
    edad = models.IntegerField()
    grado = models.CharField(max_length=20)

    def __str__(self):
        return self.nombre
```

> ✅ **Campos del modelo:**
> - `nombre`: texto (hasta 100 caracteres)
> - `edad`: número entero
> - `grado`: texto (ej: "3° semestre")

---

## 💾 **Paso 4: Crear y Aplicar Migraciones**

Esto crea la tabla en la base de datos (SQLite).

```bash
python manage.py makemigrations
python manage.py migrate
```

✅ Se crea el archivo `db.sqlite3` si no existía.

---

## 🎛️ **Paso 5: Registrar el Modelo en el Panel Admin**

Abre `estudiante/admin.py`:

```python
from django.contrib import admin
from .models import Estudiante

admin.site.register(Estudiante)
```

### Crea un superusuario (para acceder al admin)
```bash
python manage.py createsuperuser
```
- Nombre de usuario: `admin`
- Correo: (opcional)
- Contraseña: `12345678` (mínimo 8 caracteres)

✅ Accede a `http://localhost:8000/admin` después.

---

## 🖥️ **Paso 6: Crear Vistas (views.py)**

Abre `estudiante/views.py`:

```python
from django.shortcuts import render
from .models import Estudiante

def lista_estudiantes(request):
    estudiantes = Estudiante.objects.all()
    return render(request, 'estudiante/index.html', {'estudiantes': estudiantes})

def detalle_estudiante(request, id):
    estudiante = Estudiante.objects.get(id=id)
    return render(request, 'estudiante/detalle.html', {'estudiante': estudiante})
```

> - `lista_estudiantes`: muestra todos los estudiantes
> - `detalle_estudiante`: muestra un estudiante por su ID

---

## 🔗 **Paso 7: Crear URLs (proyecto y app)**

### A. En `misitio/urls.py` (del proyecto)

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('estudiante.urls')),  # Todas las rutas de "estudiante"
]
```

### B. Crea `estudiante/urls.py` (nuevo archivo)

```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.lista_estudiantes, name='lista'),
    path('estudiante/<int:id>/', views.detalle_estudiante, name='detalle'),
]
```

> - `/` → lista de estudiantes
> - `/estudiante/1/` → detalle del estudiante con ID 1

---

## 🎨 **Paso 8: Crear Plantillas (Templates)**

### 1. Crea la carpeta:
```
estudiante/templates/estudiante/
```

### 2. Crea `index.html`

**Archivo:** `estudiante/templates/estudiante/index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Mi Sitio - Estudiantes</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        h1 { color: #0056b3; }
        ul { list-style-type: none; padding: 0; }
        li { background: #f0f8ff; margin: 10px 0; padding: 10px; border-radius: 5px; }
        a { color: #0056b3; text-decoration: none; }
        a:hover { text-decoration: underline; }
    </style>
</head>
<body>
    <h1>🎓 Lista de Estudiantes</h1>
    <ul>
        {% for estudiante in estudiantes %}
            <li>
                <strong><a href="/estudiante/{{ estudiante.id }}/">{{ estudiante.nombre }}</a></strong>
                - {{ estudiante.edad }} años, {{ estudiante.grado }}
            </li>
        {% empty %}
            <li>No hay estudiantes registrados.</li>
        {% endfor %}
    </ul>
</body>
</html>
```

### 3. Crea `detalle.html`

**Archivo:** `estudiante/templates/estudiante/detalle.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Detalle - {{ estudiante.nombre }}</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        h1 { color: #0056b3; }
        .info { background: #e8f5e8; padding: 15px; border-radius: 8px; }
    </style>
</head>
<body>
    <h1>🔍 Detalle del Estudiante</h1>
    <div class="info">
        <p><strong>Nombre:</strong> {{ estudiante.nombre }}</p>
        <p><strong>Edad:</strong> {{ estudiante.edad }}</p>
        <p><strong>Grado:</strong> {{ estudiante.grado }}</p>
    </div>
    <br>
    <a href="/">← Volver a la lista</a>
</body>
</html>
```

---

## ▶️ **Paso 9: Ejecutar el Servidor**

```bash
python manage.py runserver
```

Abre tu navegador y visita:
- **Lista de estudiantes:** [http://localhost:8000](http://localhost:8000)
- **Panel admin:** [http://localhost:8000/admin](http://localhost:8000/admin) → inicia sesión

---

## ✅ **Paso 10: Agregar Estudiantes (desde el Admin)**

1. Inicia sesión en `/admin`
2. Ve a "Estudiantes" → "Añadir"
3. Ingresa datos de ejemplo:
   - Nombre: `María López`
   - Edad: `17`
   - Grado: `3° semestre`
4. Guarda
5. Repite con 2-3 estudiantes más

✅ Refresca la página principal: ¡verás la lista actualizada!

---

## 🧪 **Prueba Final: Funcionalidades Completas**

| Función | ¿Funciona? |
|--------|------------|
| Mostrar lista de estudiantes | ✅ |
| Hacer clic en un estudiante y ver su detalle | ✅ |
| Ver datos dinámicos (nombre, edad, grado) | ✅ |
| Panel admin para agregar/editar estudiantes | ✅ |
| Diseño básico con CSS | ✅ |

---

## 📌 **Consejos para el Profesor**
- Pide a los estudiantes que personalicen el diseño (colores, imágenes).
- Motívalos a agregar un campo extra (ej: `materia_favorita`).
- Pueden presentar su sitio como "Directorio Escolar".

---

## 🎁 **Ideas para Ampliar (Opcional)**
- Agregar imagen del estudiante (`ImageField`)
- Buscador por nombre
- Formulario para agregar estudiantes desde la página (sin admin)

---

Este proyecto es **totalmente funcional**, educativo y permite a los estudiantes ver resultados reales de su código. Es ideal como **proyecto final de la Unidad II**.

¿Te gustaría que te genere una **rúbrica de evaluación**, una **guía para imprimir** o un **archivo ZIP con la estructura base** para compartir con tus alumnos?
