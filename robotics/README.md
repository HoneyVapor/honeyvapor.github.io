# 🤖 Robotics++ - Plataforma Educativa Interactiva

Una plataforma educativa moderna y completa diseñada para enseñar conceptos fundamentales de programación, estructuras de datos, bases de datos y robótica a través de un sistema de evaluación interactivo y gamificado.

## 📋 Tabla de Contenidos

- [Descripción del Proyecto](#-descripción-del-proyecto)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Arquitectura del Sistema](#-arquitectura-del-sistema)
- [Características Principales](#-características-principales)
- [Instalación y Configuración](#-instalación-y-configuración)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Cursos Disponibles](#-cursos-disponibles)
- [Sistema de Evaluación](#-sistema-de-evaluación)
- [Contribución](#-contribución)
- [Licencia](#-licencia)

## 🎯 Descripción del Proyecto

**Robotics++** es una plataforma educativa interactiva que combina teoría y práctica para enseñar conceptos fundamentales de ciencias de la computación. La plataforma utiliza un sistema de evaluación gamificado con desbloqueo secuencial de contenido, quizzes interactivos y seguimiento de progreso persistente.

### Alcances de la Plataforma

- **Educación Interactiva**: Sistema de aprendizaje basado en tabs con contenido estructurado
- **Evaluación Continua**: Quizzes de 3 preguntas por tema con retroalimentación inmediata
- **Progreso Gamificado**: Desbloqueo secuencial de temas (70% mínimo para avanzar)
- **Persistencia de Datos**: Almacenamiento local del progreso del usuario
- **Interfaz Moderna**: Diseño responsivo con Material-UI y Bootstrap
- **Chatbot Integrado**: Asistencia en tiempo real para los estudiantes

## 🛠 Tecnologías Utilizadas

### Frontend Core
- **React 19.1.0** - Biblioteca principal para la interfaz de usuario
- **TypeScript 5.8.3** - Tipado estático para mayor robustez del código
- **Vite 7.0.3** - Herramienta de construcción y desarrollo rápido

### UI/UX Framework
- **Material-UI (MUI) 7.3.1** - Componentes de interfaz modernos
  - `@mui/material` - Componentes principales
  - `@mui/icons-material` - Iconografía
  - `@emotion/react` & `@emotion/styled` - Sistema de estilos CSS-in-JS
- **Bootstrap 5.3.7** - Framework CSS complementario
- **React Bootstrap 2.10.10** - Componentes Bootstrap para React

### Navegación y Routing
- **React Router DOM 7.8.2** - Enrutamiento del lado del cliente
- **@types/react-router-dom 5.3.3** - Tipos TypeScript para routing

### Herramientas de Desarrollo
- **ESLint 9.30.1** - Linter para calidad de código
- **@vitejs/plugin-react-swc 3.10.2** - Plugin de Vite con SWC para React
- **TypeScript ESLint 8.35.1** - Reglas de ESLint específicas para TypeScript

## 🏗 Arquitectura del Sistema

### Patrón de Arquitectura
La aplicación sigue una arquitectura **Component-Based** con las siguientes capas:

```
┌─────────────────────────────────────┐
│           Presentation Layer        │
│  (React Components + Material-UI)   │
├─────────────────────────────────────┤
│           Business Logic            │
│    (Custom Hooks + Context API)     │
├─────────────────────────────────────┤
│           Data Layer               │
│      (localStorage + State)        │
└─────────────────────────────────────┘
```

### Componentes Principales

#### 1. **CourseEvaluationSystem** (Componente Reutilizable)
- Sistema de evaluación centralizado
- Gestión de estado para 8 temas por curso
- Lógica de desbloqueo secuencial
- Persistencia en localStorage

#### 2. **Context API** (Gestión de Estado Global)
- Seguimiento del progreso global
- Mapeo de claves de cursos
- Estado compartido entre componentes

#### 3. **Routing System** (Navegación)
- Rutas dinámicas para cada curso
- Navegación SPA (Single Page Application)
- Lazy loading de componentes

## ✨ Características Principales

### 🎮 Sistema de Gamificación
- **Desbloqueo Secuencial**: Los temas se desbloquean al completar el anterior
- **Puntuación Mínima**: 70% requerido para avanzar
- **Iconografía Visual**: Indicadores de progreso con iconos dinámicos
- **Barra de Progreso**: Visualización del avance general del curso

### 📚 Sistema de Evaluación
- **Quizzes Interactivos**: 3 preguntas por tema
- **Retroalimentación Inmediata**: Explicaciones detalladas
- **Reintentos Ilimitados**: Posibilidad de mejorar la puntuación
- **Persistencia de Resultados**: Almacenamiento local del progreso

### 🎨 Interfaz de Usuario
- **Diseño Responsivo**: Adaptable a diferentes dispositivos
- **Tema Personalizado**: Colores institucionales (Azul UdeG + Naranja)
- **Navegación Intuitiva**: Tabs horizontales con scroll automático
- **Componentes Accesibles**: Cumplimiento de estándares de accesibilidad

### 💾 Gestión de Datos
- **localStorage**: Persistencia del progreso sin backend
- **Estado Reactivo**: Actualizaciones en tiempo real
- **Serialización JSON**: Almacenamiento estructurado de datos

## 🚀 Instalación y Configuración

### Prerrequisitos
- **Node.js** >= 18.0.0
- **npm** >= 8.0.0 o **yarn** >= 1.22.0

### Pasos de Instalación

1. **Clonar el repositorio**
```bash
git clone <repository-url>
cd robotics
```

2. **Instalar dependencias**
```bash
npm install
# o
yarn install
```

3. **Ejecutar en modo desarrollo**
```bash
npm run dev
# o
yarn dev
```

4. **Construir para producción**
```bash
npm run build
# o
yarn build
```

5. **Previsualizar build de producción**
```bash
npm run preview
# o
yarn preview
```

### Scripts Disponibles

- `npm run dev` - Servidor de desarrollo con hot reload
- `npm run build` - Construcción optimizada para producción
- `npm run lint` - Análisis de código con ESLint
- `npm run preview` - Previsualización del build de producción

## 📁 Estructura del Proyecto

```
robotics/
├── public/                     # Archivos estáticos
│   ├── img/
│   │   └── robotic.png        # Logo principal
│   └── logo.png               # Favicon
├── src/
│   ├── components/            # Componentes reutilizables
│   │   ├── CourseEvaluationSystem.tsx  # Sistema de evaluación
│   │   ├── CodeBlock.tsx      # Renderizado de código
│   │   ├── Chatbot.tsx        # Asistente virtual
│   │   ├── Header.tsx         # Navegación principal
│   │   ├── Hero.tsx           # Sección hero
│   │   ├── CurriculumSection.tsx      # Currículo
│   │   ├── SpecializationAreas.tsx    # Áreas de especialización
│   │   ├── ProgramFeatures.tsx        # Características del programa
│   │   ├── Testimonials.tsx   # Testimonios
│   │   └── Footer.tsx         # Pie de página
│   ├── pages/                 # Páginas de cursos
│   │   ├── PseudocodigoCourse.tsx
│   │   ├── EstructuraDatosCourse.tsx
│   │   ├── POONodejsCourse.tsx
│   │   ├── BaseDatosRelacionalesCourse.tsx
│   │   ├── BaseDatosNoRelacionalesCourse.tsx
│   │   ├── EcuacionesDiferencialesCourse.tsx
│   │   ├── SistemasRedesCourse.tsx
│   │   └── ProyectoFinalCourse.tsx
│   ├── context/
│   │   └── Context.tsx        # Estado global de la aplicación
│   ├── App.tsx               # Componente principal
│   ├── main.tsx              # Punto de entrada
│   └── vite-env.d.ts         # Tipos de Vite
├── package.json              # Dependencias y scripts
├── tsconfig.json            # Configuración TypeScript
├── vite.config.ts           # Configuración Vite
└── README.md                # Documentación
```

## 📖 Cursos Disponibles

La plataforma incluye 8 cursos especializados:

### 1. **Pseudocódigo** (`/robotics/curso/pseudocodigo`)
- Fundamentos de algoritmos
- Estructuras de control
- Metodología de resolución de problemas

### 2. **Estructuras de Datos** (`/robotics/curso/estructura-datos`)
- Arrays, listas, pilas y colas
- Árboles y grafos
- Algoritmos de búsqueda y ordenamiento

### 3. **POO con Node.js** (`/robotics/curso/poo-nodejs`)
- Programación orientada a objetos
- JavaScript/TypeScript avanzado
- Desarrollo backend con Node.js

### 4. **Bases de Datos Relacionales** (`/robotics/curso/base-datos-relacionales`)
- Diseño de bases de datos
- SQL avanzado
- Normalización y optimización

### 5. **Bases de Datos No Relacionales** (`/robotics/curso/base-datos-no-relacionales`)
- MongoDB y NoSQL
- Modelado de documentos
- Agregaciones y consultas

### 6. **Sistemas y Redes** (`/robotics/curso/sistemas-redes`)
- Arquitectura de sistemas
- Protocolos de red
- Seguridad informática

### 7. **Ecuaciones Diferenciales** (`/robotics/curso/ecuaciones-diferenciales`)
- Matemáticas aplicadas a robótica
- Modelado de sistemas dinámicos
- Análisis numérico

### 8. **Proyecto Final** (`/robotics/curso/proyecto-final`)
- Integración de conocimientos
- Desarrollo de proyecto completo
- Metodologías ágiles

## 🎯 Sistema de Evaluación

### Mecánica de Evaluación

#### Estructura por Curso
- **8 Temas por Curso**: Cada curso está dividido en 8 módulos temáticos
- **3 Preguntas por Tema**: Quiz de opción múltiple con retroalimentación
- **Desbloqueo Secuencial**: 70% mínimo para avanzar al siguiente tema

#### Tipos de Preguntas
- **Conceptuales**: Definiciones y teoría
- **Prácticas**: Aplicación de conocimientos
- **Análisis**: Evaluación de código y soluciones

#### Sistema de Puntuación
```typescript
interface QuizScore {
  topicId: number;
  score: number;        // Porcentaje (0-100)
  attempts: number;     // Número de intentos
  completed: boolean;   // Si superó el 70%
}
```

### Persistencia de Datos

#### LocalStorage Schema
```json
{
  "pseudocodigo-test-progress": {
    "completedTopics": [0, 1, 2],
    "quizScores": {
      "0": 85,
      "1": 92,
      "2": 78
    },
    "lastUpdated": "2024-01-15T10:30:00.000Z"
  }
}
```

## 🤝 Contribución

### Guías para Desarrolladores

#### Agregar un Nuevo Curso

1. **Crear el archivo del curso** en `src/pages/`
```typescript
import { CourseEvaluationSystem } from "../components/CourseEvaluationSystem";
import type { Topic } from "../components/CourseEvaluationSystem";

const NuevoCourse: React.FC = () => {
  const topicsData: Topic[] = [
    // 8 temas con contenido y quiz
  ];

  return (
    <CourseEvaluationSystem
      courseName="Nuevo Curso"
      courseIcon={<Icon />}
      courseDescription="Descripción del curso"
      topics={topicsData}
      localStorageKey="nuevo-curso-progress"
    />
  );
};
```

2. **Agregar la ruta** en `App.tsx`
```typescript
<Route
  path="/robotics/curso/nuevo-curso"
  element={<NuevoCourse />}
/>
```

3. **Actualizar el contexto** en `Context.tsx`
```typescript
const courseKeys = {
  // ... cursos existentes
  "nuevo-curso-progress": 8,
};
```

#### Estándares de Código

- **TypeScript**: Tipado estricto obligatorio
- **ESLint**: Seguir las reglas configuradas
- **Componentes Funcionales**: Usar hooks en lugar de clases
- **Material-UI**: Mantener consistencia visual
- **Responsive Design**: Probar en diferentes dispositivos

### Proceso de Contribución

1. Fork del repositorio
2. Crear rama feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit de cambios (`git commit -m 'Agregar nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Crear Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

---

## 🔧 Configuración Avanzada

### Variables de Entorno
```env
VITE_API_URL=https://api.roboticspp.com
VITE_CHATBOT_URL=https://roboticspp.vercel.app/api/chat
```

### Personalización del Tema
```typescript
const theme = createTheme({
  palette: {
    primary: {
      main: "#1976d2",    // Azul UdeG
    },
    secondary: {
      main: "#ff6f00",    // Naranja de acento
    },
  },
});
```

### Optimizaciones de Rendimiento
- **Code Splitting**: Lazy loading de rutas
- **Memoización**: React.memo para componentes pesados
- **Bundle Analysis**: `npm run build -- --analyze`

---

**Desarrollado con ❤️ para la educación en robótica y programación**
