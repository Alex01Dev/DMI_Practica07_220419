# 🎬 Cinemapedia — 220419

<div align="center">
  <img src="capturaa.jpg" alt="Identidad Institucional" width="200"/>

  ### Práctica 07 · Sistema de Búsqueda y Organización de Contenido Multimedia
  
  **Desarrollo de Aplicaciones Móviles**  
  **UTXJ**
  
  ---
  
  **Alumno:** Alex Amauri Marquez Canales  
  **No. de Control:** 220419
  **Periodo:** Diciembre 2025  
  **Release:** v2.0
</div>

---

## 🧩 Descripción General

**Cinemapedia** es una aplicación móvil multiplataforma creada con Flutter cuyo objetivo es consultar y explorar información relacionada con películas y series de televisión mediante el consumo de la API de **TheMovieDB (TMDB)**.  
El proyecto está estructurado bajo **Clean Architecture**, utiliza **Riverpod 3.x** para la gestión de estado y **GoRouter** para la navegación declarativa entre pantallas.

---

## 🎯 Propósito de la Práctica

### Objetivo Principal
Desarrollar un sistema de búsqueda inteligente para películas y series que permita al usuario interactuar de manera fluida con el contenido, sin comprometer la organización arquitectónica del proyecto.

### Objetivos Específicos

1. **Sistema de Búsqueda**
   - Implementar búsqueda optimizada de películas con debounce
   - Implementar búsqueda optimizada de series con debounce
   - Identificar automáticamente el tipo de contenido (cine o TV)

2. **Arquitectura y Manejo de Estado**
   - Conservar la Clean Architecture en todos los módulos
   - Implementar providers de búsqueda con Riverpod 3.x
   - Administrar correctamente estados de carga y errores

3. **Experiencia de Usuario**
   - Diseñar SearchDelegates personalizados
   - Añadir animaciones suaves y responsivas
   - Construir widgets reutilizables

---

## 🛠️ Desarrollo Realizado

### **Etapa 1: Base del Proyecto (Práctica Previa)**
- Preparación del proyecto a partir de una rama base
- Definición de entidades y modelos de actores
- Implementación de datasources para consumo de API
- Creación de mappers para deserialización de datos
- Integración de Riverpod para el manejo de actores
- Configuración de navegación con GoRouter
- Desarrollo de vistas de detalle para películas
- Visualización de reparto (cast)
- Validación general de funcionalidades

---

### **Etapa 2: Búsqueda y Módulo de Series (Práctica Actual)**

#### **2.1 Expansión de Contratos**
- Inclusión de `searchMovies()` en datasources y repositorios
- Inclusión de `searchSeries()` en datasources y repositorios
- Implementación de consultas directas a TMDB
- Adaptación de repositorios concretos

#### **2.2 Providers de Búsqueda**
- Creación de providers independientes para películas y series
- Implementación de `SearchQueryNotifier`
- Manejo de cache de resultados
- Control de estados de carga y respuesta

#### **2.3 Delegados de Búsqueda**
- Desarrollo de `SearchMovieDelegate` con:
  - Debounce de 500 ms
  - Streams reactivos
  - Indicadores de carga animados
  - Botón de limpieza
- Implementación de `SearchSeriesDelegate`
- Componentes personalizados para mostrar resultados

#### **2.4 Integración en la Interfaz**
- Mejora del `CustomAppbar` con búsqueda contextual
- Detección automática del módulo activo (películas o series)
- Navegación directa a pantallas de detalle
- Persistencia del texto de búsqueda

#### **2.5 Administración de Series**
- Implementación completa de datasources de series
- Providers para cinco categorías principales:
  - En Emisión
  - Populares
  - Mejor Valoradas
  - Próximos Estrenos
  - Series Mexicanas
- Diseño de pantalla principal con slideshow y listas horizontales
- Pantalla de detalles de series
- Indicadores visuales de progreso de carga

#### **2.6 Mejoras Visuales y UX**
- Pantalla Splash con animaciones y audio
- Clasificación por edades (G, PG, PG-13, R)
- Formateo regional de fechas (es_MX)
- Loaders con porcentaje visible
- Navegación fluida entre módulos

---

## 🗂️ Organización del Proyecto

lib/
├── config/ # Configuración global
│ ├── constants/ # Variables de entorno
│ ├── helpers/ # Utilidades de formato y ratings
│ ├── router/ # Sistema de rutas
│ └── theme/ # Tema visual
│
├── domain/ # Lógica de negocio
│ ├── datasources/ # Contratos
│ ├── entities/ # Modelos de dominio
│ └── repositories/ # Interfaces
│
├── infrastructure/ # Implementaciones concretas
│ ├── datasources/
│ ├── mappers/
│ ├── models/
│ └── repositories/
│
├── presentation/ # UI y estado
│ ├── delegates/ # Búsquedas personalizadas
│ ├── providers/ # Riverpod 3.x
│ ├── screens/ # Pantallas
│ └── widgets/ # Componentes reutilizables
│
└── main.dart # Punto de entrada


---

## 🧪 Tecnologías Utilizadas

### Núcleo
- **Flutter SDK**
- **Dart**

### Estado
- `flutter_riverpod` — Manejo de estado reactivo

### Navegación
- `go_router` — Navegación declarativa

### Comunicación
- `dio` — Cliente HTTP
- `flutter_dotenv` — Variables de entorno

### Interfaz
- `animate_do` — Animaciones
- `card_swiper` — Carruseles
- `just_audio` — Audio inicial

### Internacionalización
- `intl` — Fechas y formatos regionales

---

## ⚙️ Instalación

### Requisitos
- Flutter 3.x
- Dart 3.x
- Android Studio o VS Code
- API Key de TMDB

### Pasos

1. **Clonar proyecto**
```bash
git https://github.com/Alex01Dev/DMI_Practica07_220419.git
cd cinemapedia_220419
´´´