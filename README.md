# 🏛️ Workshop: GitHub Copilot para CFE

## Desarrollo Asistido por IA con Node.js y Angular

![GitHub Copilot](https://img.shields.io/badge/GitHub%20Copilot-Enabled-green)
![Node.js](https://img.shields.io/badge/Node.js-20+-339933)
![Angular](https://img.shields.io/badge/Angular-17+-DD0031)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6)
![Duración](https://img.shields.io/badge/Duración-3%20horas-blue)

---

## 📋 Tabla de Contenidos

- [Introducción](#-introducción)
- [Conceptos Clave de GitHub Copilot](#-conceptos-clave-de-github-copilot)
- [Pre-requisitos](#️-pre-requisitos)
- [Agenda del Workshop](#-agenda-del-workshop)
- [Laboratorio 1: Especificaciones con IA](#-laboratorio-1-especificaciones-con-ia-30-min)
- [Laboratorio 2: REST API con Node.js](#-laboratorio-2-rest-api-con-nodejs-45-min)
- [Laboratorio 3: Frontend con Angular y Agente Especializado](#-laboratorio-3-frontend-con-angular-y-agente-especializado-30-min)
- [Laboratorio 4: Pruebas y Documentación](#-laboratorio-4-pruebas-y-documentación-20-min)
- [Laboratorio 5: Características Avanzadas](#-laboratorio-5-características-avanzadas-15-min)
- [Referencia Rápida](#-referencia-rápida)
- [Recursos Adicionales](#-recursos-adicionales)

---

## 🎯 Introducción

Este workshop práctico te guiará en el desarrollo de un **Sistema de Registro de Seguro de Vehículos** para la CFE (Comisión Federal de Electricidad) utilizando **GitHub Copilot** como asistente de desarrollo. Aprenderás a:

- ✅ Generar especificaciones técnicas con IA
- ✅ Crear APIs REST con Node.js y Express
- ✅ Desarrollar frontends con Angular y estilo institucional
- ✅ Escribir pruebas unitarias automáticamente
- ✅ Crear agentes personalizados especializados
- ✅ Traducir código legacy a tecnologías modernas

### Estándares del Proyecto

| Aspecto | Estándar |
|---------|----------|
| **Tipo** | API REST |
| **Backend** | Node.js + Express + TypeScript |
| **Frontend** | Angular 17+ con TypeScript |
| **Arquitectura** | REST API modular por funcionalidad |
| **Idioma** | Español (código, comentarios, documentación) |
| **Base de datos** | En memoria (sin dependencias externas) |
| **Estilos** | Bootstrap 5 |

---

## 🧠 Conceptos Clave de GitHub Copilot

### ¿Qué es @workspace?

El **@workspace** es un participante de chat que proporciona contexto sobre todo tu espacio de trabajo (proyecto) a GitHub Copilot.

#### ¿Para qué sirve?

| Función | Ejemplo |
|---------|---------|
| **Buscar código** | `@workspace ¿dónde se define la interfaz Poliza?` |
| **Entender el proyecto** | `@workspace ¿qué hace este proyecto?` |
| **Encontrar patrones** | `@workspace ¿cómo se implementan las rutas?` |
| **Generar código contextual** | `@workspace crea una nueva ruta similar a las existentes` |

#### ¿Cuándo usarlo?

- ✅ Cuando necesitas que Copilot entienda la estructura de tu proyecto
- ✅ Para generar código que siga los patrones existentes
- ✅ Para buscar implementaciones específicas
- ✅ Para preguntas sobre arquitectura del proyecto

#### Ejemplo práctico:

```
# Sin @workspace - Copilot no conoce tu proyecto
"Crea endpoints para pólizas de seguro"
→ Genera código genérico

# Con @workspace - Copilot analiza tu proyecto
"@workspace Crea endpoints para pólizas de seguro"
→ Genera código siguiendo TUS patrones y convenciones
```

---

### Modos de GitHub Copilot Chat

GitHub Copilot tiene **tres modos principales** de operación. Es crucial entender cuándo usar cada uno:

#### 1️⃣ Modo Ask (Preguntar) 💬

| Característica | Descripción |
|----------------|-------------|
| **Ícono** | 💬 Burbuja de mensaje |
| **Función** | Solo responde preguntas, **NO modifica archivos** |
| **Uso ideal** | Explorar, entender, planificar, aprender |

**Cuándo usar Modo Ask:**
- 🔍 Investigar cómo implementar algo
- 📚 Entender código existente
- 🤔 Comparar opciones de diseño
- 📋 Planificar antes de implementar

**Ejemplo:**
```
[Modo Ask]
"¿Cuál es la mejor forma de implementar autenticación JWT en Node.js con Express?"

→ Copilot EXPLICA las opciones pero NO crea archivos
```

---

#### 2️⃣ Modo Agent (Agente) 🤖

| Característica | Descripción |
|----------------|-------------|
| **Ícono** | 🤖 Robot o chispa |
| **Función** | **PUEDE crear y modificar archivos** automáticamente |
| **Uso ideal** | Implementar cambios, crear código, refactorizar |

**Cuándo usar Modo Agent:**
- ✏️ Crear nuevos archivos
- 🔧 Modificar código existente
- 🏗️ Implementar funcionalidades completas
- 🔄 Refactorizar código

**Ejemplo:**
```
[Modo Agent]
"Crea rutas Express para pólizas de seguro con operaciones CRUD"

→ Copilot CREA el archivo poliza.routes.ts con todo el código
```

---

#### 3️⃣ Modo Plan (Planificar) 📋

| Característica | Descripción |
|----------------|-------------|
| **Ícono** | 📋 Lista o documento |
| **Función** | Genera un **plan detallado ANTES de ejecutar** |
| **Uso ideal** | Tareas complejas que involucran múltiples archivos |

**Cuándo usar Modo Plan:**
- 📁 Crear múltiples archivos relacionados
- 🏛️ Implementar funcionalidades que cruzan capas
- 🔍 Revisar cambios antes de aplicarlos
- ⚠️ Tareas donde quieres control sobre cada paso

**Ejemplo:**
```
[Modo Plan]
"Implementa la funcionalidad completa de Coberturas con interfaz, DTOs 
y rutas Express"

→ Copilot MUESTRA el plan:
  1. Crear cobertura.model.ts (interfaz)
  2. Crear cobertura.dto.ts (DTOs)
  3. Crear cobertura.routes.ts (rutas Express)
  4. Registrar rutas en app.ts

→ Tú APRUEBAS cada paso antes de que se ejecute
```

---

#### Comparativa de Modos

| Aspecto | Ask 💬 | Agent 🤖 | Plan 📋 |
|---------|--------|----------|---------|
| Modifica archivos | ❌ No | ✅ Sí | ✅ Sí (con aprobación) |
| Velocidad | Rápido | Rápido | Más lento |
| Control | N/A | Bajo | Alto |
| Ideal para | Aprender | Implementar | Tareas complejas |
| Riesgo | Ninguno | Medio | Bajo |

---

### Agentes Personalizados (@nombre-agente)

Los **agentes personalizados** son "expertos" que puedes crear para tareas específicas. Se definen en archivos Markdown en `.github/agents/`.

#### ¿Cómo funcionan?

1. Creas un archivo `.github/agents/mi-agente.md`
2. Defines el rol, reglas y conocimiento del agente
3. Lo invocas con `@mi-agente` en el chat

#### ¿Para qué sirven?

| Uso | Ejemplo |
|-----|---------|
| **Especialización** | Agente experto en frontend con estilos CFE |
| **Consistencia** | Agente que siempre sigue los estándares del equipo |
| **Revisión** | Agente que revisa código según checklist |
| **Dominio** | Agente que conoce terminología específica de seguros |

#### Ejemplo de agente:

```markdown
# .github/agents/frontend-cfe.md

# Agente: Frontend CFE

## Rol
Eres experto en desarrollo frontend para la CFE.

## Reglas
- Usar colores institucionales (#003B71, #00A651)
- Todo el texto en español
- Componentes accesibles (WCAG AA)
```

**Uso:**
```
@frontend-cfe Crea un componente de tarjeta para mostrar pólizas de seguro
```

---

### Comandos Especiales (/comando)

| Comando | Descripción | Ejemplo |
|---------|-------------|---------|
| `/tests` | Genera pruebas unitarias | Selecciona código → `/tests` |
| `/doc` | Genera documentación JSDoc | Selecciona clase → `/doc` |
| `/fix` | Propone corrección de errores | Selecciona código con error → `/fix` |
| `/explain` | Explica código seleccionado | Selecciona código → `/explain` |
| `/new` | Crea nuevo archivo/proyecto | `/new crear interfaz Poliza` |

---

## 🛠️ Pre-requisitos

### Software Necesario

```bash
# Verificar instalaciones
node --version    # Debe ser 20.x o superior
npm --version     # Viene con Node.js
code --version    # Visual Studio Code
git --version     # Git
```

> **📝 NOTA:** Este taller usa **almacenamiento en memoria** para no requerir instalación de software adicional como MongoDB, PostgreSQL o MySQL. Los datos se pierden al reiniciar la aplicación, pero es perfecto para desarrollo y pruebas.

### Extensiones de VS Code

1. **GitHub Copilot** - Extensión principal
2. **GitHub Copilot Chat** - Chat integrado
3. **Angular Language Service** - Soporte para Angular
4. **ESLint** - Linting de TypeScript/JavaScript

### Cuenta de GitHub

- Necesitas una cuenta con acceso a GitHub Copilot
- Puede ser licencia individual, de organización o educativa

---

## 📅 Agenda del Workshop

| Tiempo | Módulo | Descripción | Modo Copilot |
|--------|--------|-------------|--------------|
| 0:00 - 0:15 | Introducción | Setup y configuración | - |
| 0:15 - 0:45 | Lab 1 | Especificaciones y diseño | **Ask** → **Agent** |
| 0:45 - 1:30 | Lab 2 | REST API para seguros de vehículos | **Agent** + **Plan** |
| 1:30 - 1:45 | ☕ Break | Descanso | - |
| 1:45 - 2:15 | Lab 3 | Frontend Angular con Agente | **@frontend-cfe** |
| 2:15 - 2:35 | Lab 4 | Pruebas y documentación | **Agent** |
| 2:35 - 2:50 | Lab 5 | Agentes y traducción | **Custom Agents** |
| 2:50 - 3:00 | Cierre | Q&A y recursos | - |

---

## 🔬 LABORATORIO 1: Especificaciones con IA (30 min)

### Objetivos
- ✅ Usar Modo Ask para explorar y diseñar
- ✅ Cambiar a Modo Agent para crear archivos
- ✅ Generar especificaciones técnicas completas

---

### Paso 1.1: Crear estructura inicial

**🤖 PROMPT en Modo Agent:**

```
Crea la estructura de carpetas inicial para el proyecto:
- docs/especificaciones
- src
- .github/agents
```

**📝 Alternativa manual (si el agente no ejecuta los comandos):**

```bash
mkdir -p docs/especificaciones
mkdir -p src
mkdir -p .github/agents
```

---

### Paso 1.2: Explorar con MODO ASK 🔍

> **💡 IMPORTANTE:** Asegúrate de estar en **Modo Ask** (ícono de mensaje 💬 en Copilot Chat). Este modo NO modifica archivos, solo responde preguntas.

**📍 Cómo activar Modo Ask:**
1. Abre Copilot Chat (`Ctrl+Shift+I`)
2. Busca el selector de modo en la parte superior
3. Selecciona "Ask" o el ícono de mensaje

**🤖 PROMPT - Copia y pega en Copilot Chat:**

```
Soy arquitecto de software en la CFE (Comisión Federal de Electricidad de México) y necesito diseñar un sistema de registro de seguro de vehículos. 

Ayúdame a entender:

1. ¿Qué entidades principales necesitaría para un sistema que gestione:
   - Diferentes tipos de seguros de vehículos (Responsabilidad Civil, Comprensivo, Todo Riesgo, Básico)
   - Coberturas con diferentes tipos y montos
   - Registro de vehículos con datos técnicos (placa, marca, modelo, chasis)
   - Datos de asegurados con ubicación por estado y municipio
   - Gestión de reclamos
   - Estadísticas agregadas por estado

2. ¿Qué endpoints REST serían necesarios?

3. ¿Cómo organizar esto usando Node.js con Express y TypeScript?

4. ¿Qué consideraciones de seguridad debo tener para datos de seguros y datos personales?
```

**📝 Observa:** Copilot responde con información detallada pero **NO crea ningún archivo**. Esto es ideal para la fase de exploración.

---

### Paso 1.3: Refinar el diseño con preguntas de seguimiento

> **💡 NOTA:** Seguimos en Modo Ask para profundizar en el diseño.

**🤖 PROMPT de seguimiento:**

```
Gracias. Ahora explícame con más detalle:

1. ¿Cómo organizarías la funcionalidad de Pólizas usando Express con TypeScript?
   - Muéstrame la estructura de carpetas
   - ¿Qué archivos tendría cada funcionalidad?

2. ¿Cómo agrupar las rutas con express.Router?

3. Dame un ejemplo de cómo se vería un endpoint POST para crear una póliza de seguro con Express y TypeScript
```

---

### Paso 1.4: Cambiar a MODO AGENT para implementar 🤖

> **💡 IMPORTANTE:** Ahora cambia a **Modo Agent** (ícono de robot 🤖). Este modo **PUEDE crear y modificar archivos**.

**📍 Cómo activar Modo Agent:**
1. En Copilot Chat, busca el selector de modo
2. Selecciona "Agent" o el ícono de robot/chispa

**🤖 PROMPT en Modo Agent:**

```
Ahora sí, crea la especificación técnica completa del sistema.

Crea el archivo docs/especificaciones/especificacion-sistema.md con:

1. **Visión General**
   - Sistema REST API + Frontend para gestionar registro de seguros de vehículos de la CFE
   
2. **Estándares Técnicos**
   | Aspecto | Estándar |
   |---------|----------|
   | Tipo | API REST |
   | Backend | Node.js + Express + TypeScript |
   | Frontend | Angular 17+ con TypeScript |
   | Arquitectura | REST API modular por funcionalidad |
   | Idioma | Español |

3. **Requisitos Funcionales**
   - CRUD de pólizas de seguro (Responsabilidad Civil, Comprensivo, Todo Riesgo, Básico)
   - Registro de vehículos con datos técnicos (placa, marca, modelo, año, chasis)
   - Gestión de coberturas con tipos y montos máximos
   

4. **Modelo de Datos** (diagrama Mermaid)

5. **Estructura de carpetas del proyecto**

6. **Endpoints de la API** (tabla completa)
```

**✅ Resultado esperado:** Copilot crea el archivo `docs/especificaciones/especificacion-sistema.md` automáticamente.

---

### Paso 1.5: Crear modelo de dominio con diagrama

**🤖 PROMPT en Modo Agent:**

```
Crea el archivo docs/especificaciones/modelo-dominio.md con:

1. Diagrama Mermaid de entidad-relación para:
   - Poliza (id, numeroPoliza, vehiculoId, aseguradoId, tipoSeguro, fechaInicio, fechaVencimiento, estado, montoAsegurado, prima)
   - Vehiculo (id, placa, marca, modelo, anio, numeroChasis, tipoVehiculo, color)
   - Cobertura (id, polizaId, nombre, tipoCobertura, montoMaximo, deducible, esObligatoria)
   - DetalleCobertura (id, coberturaId, descripcion, valor)
   - Asegurado (id, curp, nombreCompleto, estado, municipio, telefono, correo)
   - Reclamo (id, polizaId, fechaIncidente, descripcion, montoReclamado, estadoReclamo)
   - EstadisticaEstadol (id, estado, totalPolizas, montoTotalAsegurado)

2. Descripción de cada entidad en español

3. Reglas de negocio

4. Catálogo de tipos (TipoSeguro, TipoCobertura, EstadoPoliza, EstadoReclamo, TipoVehiculo)
```

---

### Paso 1.6: Definir contratos de API

> **💡 NOTA:** Usamos `#file:` para referenciar archivos existentes y que Copilot use ese contexto.

**🤖 PROMPT en Modo Agent:**

```
Basándote en los endpoints definidos en #file:docs/especificaciones/especificacion-sistema.md, crea el archivo docs/especificaciones/contratos-api.md con la especificación detallada.

Para cada endpoint incluye:
- Esquema de solicitud (JSON)
- Esquema de respuesta (JSON)  
- Códigos de estado HTTP
- Ejemplos de uso
```

**✅ Verificar antes de continuar:**
- [ ] Existen los 3 archivos en `docs/especificaciones/`
- [ ] Los diagramas Mermaid se renderizan correctamente en VS Code
- [ ] La tabla de endpoints está completa

---

### 🛠️ Troubleshooting Lab 1

| Problema | Solución |
|----------|----------|
| Copilot no crea archivos | Verifica que estés en **Modo Agent**, no en Modo Ask |
| Los diagramas Mermaid no se ven | Instala la extensión "Markdown Preview Mermaid Support" |
| Copilot responde en inglés | Verifica que `.github/copilot-instructions.md` esté configurado con idioma español (Lab 2.1). Si aún no lo has creado, agrega "Responde en español" al final del prompt |

---

## 🔬 LABORATORIO 2: REST API con Node.js (45 min)

### Objetivos
- ✅ Crear estructura de proyecto Node.js con TypeScript
- ✅ Implementar API REST con Express
- ✅ Usar Modo Plan para tareas complejas
- ✅ Generar código siguiendo estándares

---

### Paso 2.1: Crear instrucciones de Copilot

> **⚠️ IMPORTANTE:** Este paso debe ejecutarse **ANTES** de crear código para que Copilot siga los estándares desde el inicio.

**🤖 PROMPT en Modo Agent:**

```
Crea el archivo .github/copilot-instructions.md con instrucciones para que Copilot actúe como experto en Node.js para la CFE:

# Instrucciones para GitHub Copilot - Proyecto CFE Seguros de Vehículos

## Alcance del Proyecto
- Este proyecto se limita a dos funcionalidades: **Pólizas** y **Coberturas**
- NO implementar autenticación, autorización ni seguridad (JWT, OAuth, etc.)
- NO implementar otras entidades (vehículos, asegurados, reclamos, etc.) a menos que se indique explícitamente
- Todos los datos se almacenan **en memoria** (arrays y Maps de TypeScript). No usar bases de datos externas

## Idioma
- Todo el código, comentarios y documentación debe estar en **español**
- Mensajes de error en español
- Nombres de variables y métodos en español (excepto palabras técnicas estándar como get, set, async)

## Estándares de Código
| Aspecto | Estándar |
|---------|----------|
| Runtime | Node.js 20+ |
| Lenguaje | TypeScript 5.x estricto |
| Framework | Express.js |
| Arquitectura | REST API modular por funcionalidad |
| Async | Usar async/await en todas las operaciones I/O |
| Base de datos | Almacenamiento en memoria (arrays/Maps, sin dependencias externas de BD) |
| Seguridad | No implementar. Sin autenticación ni autorización |

## Nomenclatura
- Interfaces y tipos: PascalCase en español (Poliza, Cobertura, CrearPolizaSolicitud)
- Variables y funciones: camelCase en español (obtenerPolizas, crearCobertura)
- Archivos: kebab-case (poliza.routes.ts, cobertura.model.ts)
- DTOs: EntidadDto, CrearEntidadSolicitud, ActualizarEntidadSolicitud

## Manejo de Errores
- Retornar objetos de error consistentes con código y mensaje en español
- Usar middleware de manejo de errores en Express
- No implementar manejo de errores de autenticación/autorización
```

---

### Paso 2.2: Crear el proyecto Node.js con TypeScript

> **💡 DEMOSTRACIÓN:** Este paso muestra cómo GitHub Copilot puede interactuar con la terminal para ejecutar comandos.

**🤖 PROMPT en Modo Agent:**

```
Crea la estructura del proyecto Node.js en la carpeta src/api:

1. Inicializa un proyecto npm con TypeScript
2. Instala las dependencias: express, cors, swagger-jsdoc, swagger-ui-express, uuid
3. Instala las dev dependencies: typescript, ts-node, @types/express, @types/cors, @types/swagger-jsdoc, @types/swagger-ui-express, @types/uuid, nodemon
4. Configura tsconfig.json con opciones estrictas
5. Configura los scripts en package.json:
   - "dev": nodemon con ts-node
   - "build": tsc
   - "start": node dist/index.js
6. Crea la estructura de carpetas:
   src/api/src/
     funcionalidades/
       polizas/
       vehiculos/
     datos/
     middlewares/
     index.ts

Ejecuta los comandos en la terminal
```

**✅ Observa:** Copilot debería ejecutar los comandos `npm` automáticamente en la terminal integrada.

**📝 Alternativa manual:**

```bash
mkdir -p src/api && cd src/api
npm init -y
npm install express cors swagger-jsdoc swagger-ui-express uuid
npm install -D typescript ts-node @types/express @types/cors @types/swagger-jsdoc @types/swagger-ui-express @types/uuid nodemon @types/node
npx tsc --init --strict --target ES2022 --module commonjs --outDir ./dist --rootDir ./src --resolveJsonModule --esModuleInterop
mkdir -p src/funcionalidades/polizas src/funcionalidades/vehiculos src/datos src/middlewares
```

---

### Paso 2.3: Usar MODO PLAN para tarea compleja 📋

> **💡 IMPORTANTE:** Activa **Modo Plan** (ícono de lista 📋). Este modo genera un plan detallado ANTES de ejecutar, permitiéndote revisar y aprobar cada paso.

**📍 Cómo activar Modo Plan:**
1. En Copilot Chat, busca el selector de modo
2. Selecciona "Plan" o "Edit" con planificación

**🤖 PROMPT en Modo Plan:**

```
Basándote en la especificación #file:docs/especificaciones/especificacion-sistema.md y el modelo de dominio #file:docs/especificaciones/modelo-dominio.md, implementa la funcionalidad principal de gestión de pólizas de seguro usando Express con TypeScript.

Muéstrame el plan antes de ejecutar
```

**📝 Observa el plan:** Copilot analizará las especificaciones y mostrará un plan como:

```
📋 Plan de implementación:

1. ✏️ Crear src/api/src/funcionalidades/polizas/poliza.model.ts
   - Interfaces y tipos (Poliza, TipoSeguro, EstadoPoliza)

2. ✏️ Crear src/api/src/funcionalidades/polizas/poliza.dto.ts
   - DTOs para transferencia de datos

3. ✏️ Crear src/api/src/funcionalidades/polizas/poliza.routes.ts
   - Rutas Express con Router

¿Aprobar plan?
```

**Revisa y aprueba** cada paso del plan.

**✅ Verificar:** Después de aprobar el plan, verifica que se crearon los 3 archivos en `src/api/src/funcionalidades/polizas/`

---

### Paso 2.4: Implementar almacenamiento en memoria

**🤖 PROMPT en Modo Agent:**

```
@workspace Basándote en las interfaces creadas, crea el almacenamiento de datos en src/api/src/datos/:

1. almacen-datos.ts — Clase que gestiona los datos en memoria usando arrays tipados:
   - Arrays para Poliza (y Vehiculo si ya existe la interfaz)
   - Métodos CRUD genéricos tipados

2. datos-semilla.ts — Función pública inicializarDatosSemilla() que:
   - Verifique si ya existen datos
   - Si no hay datos, agregue 3 pólizas de ejemplo con datos realistas
   - Retorne los datos inicializados
```

---

### Paso 2.5: Configurar el servidor Express (index.ts)

**🤖 PROMPT en Modo Agent:**

```
@workspace Crea src/api/src/index.ts para configurar el servidor Express:

1. Configuración de Express con TypeScript:
   - Parseo de JSON con express.json()
   - CORS habilitado para desarrollo (permitir localhost)

2. Swagger/OpenAPI con swagger-jsdoc y swagger-ui-express:
   - Título: "API de Seguros de Vehículos - CFE"
   - Versión: v1
   - Disponible en /api-docs

3. Middleware:
   - Middleware de manejo de errores global
   - Logging básico de peticiones

4. Registrar las rutas:
   - app.use('/api/v1/polizas', polizaRoutes)

5. Inicializar datos semilla al arrancar:
   - Llamar inicializarDatosSemilla()

6. Escuchar en puerto 3000 (o variable de entorno PORT)
```

---

### Paso 2.6: Verificar dependencias instaladas

> **💡 DEMOSTRACIÓN:** Copilot puede verificar e instalar paquetes npm directamente.

**🤖 PROMPT en Modo Agent:**

```
Verifica que todas las dependencias necesarias estén instaladas en el proyecto src/api.
Si falta alguna, instálala.
```

**📝 Alternativa manual:**

```bash
cd src/api
npm install
```

> **📝 NOTA:** Usamos almacenamiento en memoria en lugar de MongoDB o PostgreSQL para no requerir instalación de software adicional. Los datos se almacenan en arrays y se pierden al reiniciar, pero los datos semilla se cargan automáticamente al iniciar.

---

### Paso 2.7: Ejecutar y probar la API

> **💡 DEMOSTRACIÓN:** Copilot puede compilar y ejecutar proyectos Node.js.

**🤖 PROMPT en Modo Agent:**

```
Compila y ejecuta el proyecto de la API Node.js en modo desarrollo
```

**📝 Alternativa manual:**

```bash
cd src/api
npm run dev
```

Abre en el navegador: `http://localhost:3000/api-docs`

**✅ Verificar:**
- Swagger UI muestra todos los endpoints
- GET /api/v1/polizas retorna las pólizas semilla
- POST /api/v1/polizas puede crear nuevas pólizas

> **💡 Si algo falla:** Revisa la consola de VS Code para ver errores de compilación o runtime.

---

### Paso 2.8: Implementar funcionalidad de Vehículos

**🤖 PROMPT en Modo Plan:**

```
Basándote en #file:docs/especificaciones/modelo-dominio.md, implementa la funcionalidad de Vehículos con Express y TypeScript.

Crea en src/api/src/funcionalidades/vehiculos/:
1. vehiculo.model.ts — Interfaces con propiedades: placa, marca, modelo, anio, numeroChasis, tipoVehiculo, color
2. vehiculo.dto.ts — DTOs correspondientes
3. vehiculo.routes.ts — Rutas Express con Router para "/api/v1/vehiculos"
4. Actualizar el almacén de datos con el nuevo array de vehículos
5. Registrar app.use('/api/v1/vehiculos', vehiculoRoutes) en index.ts

Muéstrame el plan primero
```

**✅ Verificar antes de continuar:**
- [ ] La API compila sin errores (`npm run build`)
- [ ] Swagger muestra endpoints de Pólizas y Vehículos
- [ ] Los datos semilla se cargan al iniciar

---

### 🛠️ Troubleshooting Lab 2

| Problema | Solución |
|----------|----------|
| Error "Cannot find module" | Ejecuta `npm install` en la carpeta del proyecto |
| Error de tipos TypeScript | Verifica que los `@types/` estén instalados como devDependencies |
| Swagger no aparece | Asegúrate de que `app.use('/api-docs', ...)` esté antes de `app.listen()` |
| Puerto en uso | Cambia el puerto con `PORT=3001 npm run dev` o cierra otras instancias |
| Datos semilla no aparecen | Verifica que `inicializarDatosSemilla()` se llame en `index.ts` |

---

## 🔬 LABORATORIO 3: Frontend con Angular y Agente Especializado (30 min)

> **⚠️ PRERREQUISITO:** Este laboratorio requiere haber completado el **Laboratorio 2**. Necesitas:
> - El proyecto API Node.js creado y funcionando
> - El archivo `.github/copilot-instructions.md` configurado

### Objetivos
- ✅ Crear un agente personalizado especializado
- ✅ Usar el agente para desarrollo frontend
- ✅ Aplicar estilos institucionales de la CFE
- ✅ Consumir la API REST desde Angular

---

### Paso 3.1: Crear el Agente de Frontend (versión básica) 🤖

> **💡 CONCEPTO:** Los agentes personalizados permiten crear "expertos" especializados que Copilot puede usar para tareas específicas.

**🤖 PROMPT en Modo Agent:**

```
Crea el archivo .github/agents/frontend-cfe.md con un agente básico para desarrollo frontend:

# Agente: Frontend CFE (@frontend-cfe)

## Rol
Eres un experto en desarrollo frontend con Angular para la CFE (Comisión Federal de Electricidad de México).

## Idioma
- Todo el código, comentarios y textos de interfaz deben estar en **español**
- Usar terminología oficial de seguros (Póliza, Cobertura, Asegurado, Reclamo, Prima, etc.)

## Tecnologías
- Angular 17+ con TypeScript
- Bootstrap 5 y CSS3 con variables personalizadas (custom properties)
- HTML5 semántico
- Angular Router para navegación
- HttpClient para comunicación con API

## Accesibilidad (WCAG AA)
- Contraste mínimo 4.5:1 para texto
- Todos los elementos interactivos accesibles por teclado
- Atributos ARIA donde corresponda

## Responsive Design
- Enfoque Mobile First
- Breakpoints: Móvil (< 576px), Tablet (576px - 992px), Desktop (> 992px)

## Reglas Importantes
1. SIEMPRE incluir estados de carga (spinners, skeletons)
2. SIEMPRE manejar errores con mensajes amigables en español
3. NUNCA usar inglés en textos visibles para el usuario
4. SIEMPRE documentar componentes con comentarios en español
5. Usar componentes standalone de Angular cuando sea posible
```

---

### Paso 3.2: Analizar el sitio de la CFE con screenshot 📸 *(Opcional)*

> **💡 DEMOSTRACIÓN:** Copilot puede analizar imágenes para extraer información de diseño como colores, tipografía y estilos.
>
> **📝 NOTA:** Los pasos 3.2 y 3.3 son opcionales pero recomendados. Si los omites, el agente usará colores institucionales genéricos definidos en el paso 3.1.

**📍 Instrucciones:**
1. Abre el sitio oficial de la CFE: https://www.cfe.mx/
2. Toma un screenshot de la página principal (usa `Win+Shift+S` en Windows o `Cmd+Shift+4` en Mac)
3. Guarda la imagen o tenla en el portapapeles

**🤖 PROMPT en Modo Agent (adjunta el screenshot):**

```
Analiza este screenshot del sitio oficial de la CFE y extrae la siguiente información de diseño:

1. **Paleta de colores**: Identifica los colores principales usados en:
   - Header/navegación
   - Botones y llamadas a la acción
   - Fondos y textos
   - Acentos y elementos secundarios
   Proporciona los códigos hexadecimales exactos o aproximados

2. **Tipografía**: 
   - Fuentes utilizadas (o similares si no son identificables)
   - Jerarquía de tamaños (h1, h2, h3, texto base)

3. **Componentes UI identificados**:
   - Estilo de header y navegación
   - Estilo de tarjetas/cards
   - Estilo de botones
   - Estilo de footer

4. **Espaciado y layout**:
   - Márgenes y paddings aproximados
   - Estructura de grid

Genera esta información en formato que pueda agregar al agente frontend-cfe.md
```

---

### Paso 3.3: Actualizar el agente con estilos de la CFE 🎨 *(Opcional)*

> **💡 NOTA:** Ahora actualizamos el agente básico con la información extraída del screenshot. (Requiere haber completado el paso 3.2)

**🤖 PROMPT en Modo Agent:**

```
Actualiza el archivo #file:.github/agents/frontend-cfe.md agregando la información de diseño extraída del screenshot.

Agrega las siguientes secciones después de "Responsive Design":

## Paleta de Colores Instituciona la CFE
(Incluye los colores identificados con sus códigos hex y uso recomendado)

## Tipografía
(Incluye las fuentes y escala de tamaños)

## Componentes Estándar
Describe el estilo visual para:
- Header Institucional
- Footer Institucional  
- Tarjetas (Cards)
- Botones
- Tablas

## Estructura de Archivos Angular
Organiza los componentes Angular así:
/src
  /app
    /componentes
      /layout
      /paginas
      /compartidos
    /servicios
    /modelos
    /guards
  /assets
    /css
    /img
  /environments
```

**✅ Resultado:** El agente ahora tiene toda la información de diseño institucional de la CFE extraída directamente del sitio oficial.

---

### Paso 3.4: Crear proyecto Angular

**🤖 PROMPT en Modo Agent:**

```
Crea un proyecto Angular en la carpeta src/cfe-seguros-web usando Angular CLI.
Configúralo con routing habilitado, SCSS como preprocesador de estilos, y componentes standalone.
Agrega Bootstrap 5 como dependencia.
El proyecto será el frontend del sistema de seguros de vehículos de la CFE.
```

**📝 Alternativa manual:**

```bash
cd src
npx @angular/cli new cfe-seguros-web --routing --style=scss --standalone --skip-tests=false
cd cfe-seguros-web
npm install bootstrap@5
```

> **💡 NOTA:** Agrega Bootstrap en `angular.json` dentro de `styles`:
> ```json
> "styles": [
>   "node_modules/bootstrap/dist/css/bootstrap.min.css",
>   "src/styles.scss"
> ]
> ```

**✅ Verificar:** El proyecto inicia correctamente (`ng serve`)

---

### Paso 3.5: Crear la aplicación frontend completa 🎨

> **💡 IMPORTANTE:** Usa el agente especializado escribiendo `@frontend-cfe` al inicio del prompt. Con un solo prompt, Copilot generará toda la estructura del frontend.

**🤖 PROMPT con Agente:**

```
@frontend-cfe Crea la aplicación frontend completa del Sistema de Seguros de Vehículos de la CFE dentro del proyecto Angular en src/cfe-seguros-web.

Necesito que generes TODO lo siguiente en un solo paso:

## 1. Estilos (src/assets/css/tema-cfe.scss)
- Variables SCSS con la paleta de colores institucional de la CFE
- Reset CSS básico y tipografía base (Google Fonts: Montserrat y Open Sans)
- Clases para componentes: botones, tarjetas, header, footer, tablas
- Animaciones para transiciones y estados de carga

## 2. Layout Principal (src/app/componentes/layout/)
- HeaderComponent: header institucional con logo, título "Sistema de Seguros de Vehículos" y navegación con routerLink
- FooterComponent: footer con enlaces legales, contacto y copyright "© CFE"
- LayoutComponent: layout wrapper que use <router-outlet> para las páginas

## 3. Componentes Reutilizables (src/app/componentes/compartidos/)
- **TarjetaPolizaComponent**: Card con número de póliza, tipo de seguro, vehículo, fechas, badge de estado con color, y botones de acción (ver, editar, eliminar). Usa @Input() para recibir datos y @Output() para emitir eventos
- **IndicadorCargaComponent**: Spinner con mensaje personalizable via @Input()
- **ModalConfirmacionComponent**: Modal Bootstrap para confirmar eliminación de pólizas

## 4. Página de Inicio (src/app/componentes/paginas/inicio/) — ruta "/"
- Sección hero con título y botón "Registrar Nuevo Seguro" con routerLink
- Estadísticas destacadas (pólizas activas, vehículos asegurados)
- Pólizas destacadas usando TarjetaPolizaComponent con datos de ejemplo

## 5. Página de Pólizas (src/app/componentes/paginas/polizas/) — ruta "/polizas"
- Filtros: dropdown tipo de seguro, dropdown estado, búsqueda por texto con ngModel o Reactive Forms
- Grid responsive de TarjetaPolizaComponent usando *ngFor
- Botón "Nueva Póliza" que abre formulario/modal
- Acciones por póliza: ver detalle, editar, eliminar (con confirmación)
- Estados: carga, vacío, error con reintento

## 6. Configuración
- app.routes.ts con rutas: /, /polizas, /polizas/:id
- app.config.ts con provideRouter y provideHttpClient
- Importar Bootstrap 5 en angular.json y tema-cfe.scss en styles.scss
- index.html con meta tags en español, título "Sistema de Seguros de Vehículos - CFE"
- environment.ts con apiUrl: 'http://localhost:3000'

Usa datos de ejemplo hardcodeados (mock) para todas las páginas por ahora.
Todos los textos en español. Usa componentes standalone.
```

---

### Paso 3.6: Crear servicio HTTP y conectar con la API

> **💡 CONCEPTO:** Ahora conectamos el frontend con la API REST creada en el Laboratorio 2 mediante un servicio Angular.

**🤖 PROMPT con Agente:**

```
@frontend-cfe Crea el servicio HTTP para conectar el frontend con la API de seguros de vehículos y reemplaza los datos mock.

## API a consumir
El frontend consume la API REST de Node.js:
- GET /api/v1/polizas — listar pólizas
- GET /api/v1/polizas/{id} — obtener póliza por ID
- POST /api/v1/polizas — crear nueva póliza
- PUT /api/v1/polizas/{id} — actualizar póliza
- DELETE /api/v1/polizas/{id} — eliminar póliza
- GET /api/v1/vehiculos — listar vehículos

## Implementación requerida

### 1. Modelos TypeScript (src/app/modelos/)
- poliza.model.ts: interfaces Poliza, CrearPolizaSolicitud, ActualizarPolizaSolicitud
- vehiculo.model.ts: interfaz Vehiculo

### 2. Servicio (src/app/servicios/poliza.service.ts)
Servicio Angular inyectable con HttpClient:
- obtenerPolizas(): Observable<Poliza[]>
- obtenerPolizaPorId(id: string): Observable<Poliza>
- crearPoliza(solicitud: CrearPolizaSolicitud): Observable<Poliza>
- actualizarPoliza(id: string, solicitud: ActualizarPolizaSolicitud): Observable<Poliza>
- eliminarPoliza(id: string): Observable<void>

### 3. Servicio (src/app/servicios/vehiculo.service.ts)
- obtenerVehiculos(): Observable<Vehiculo[]>

URL base desde environment.apiUrl con manejo de errores usando catchError y throwError.

### 4. Actualizar las páginas
- Reemplaza los datos mock en InicioComponent y PolizasComponent para que consuman los servicios reales
- Mantén los estados de carga y error que ya existen
- Usa el patrón subscribe / async pipe para los observables
```

---

### Paso 3.7: Ejecutar el Frontend

**🤖 PROMPT en Modo Agent:**

```
Ejecuta ambos proyectos:
1. Primero inicia la API Node.js en una terminal
2. Luego inicia el frontend Angular en otra terminal
```

**📝 Alternativa manual:**

```bash
# Terminal 1: Ejecutar API
cd src/api
npm run dev

# Terminal 2: Ejecutar Frontend
cd src/cfe-seguros-web
ng serve
```

Abre el navegador en la URL indicada (generalmente `http://localhost:4200`).

**✅ Verificar antes de continuar:**
- [ ] El frontend carga sin errores en el navegador
- [ ] Los estilos CFE se aplican correctamente
- [ ] La página de inicio muestra las secciones diseñadas
- [ ] El listado de pólizas carga datos desde la API
- [ ] Las operaciones CRUD (crear, ver, editar, eliminar) funcionan

---

### 🛠️ Troubleshooting Lab 3

| Problema | Solución |
|----------|----------|
| El agente @frontend-cfe no responde | Recarga VS Code después de crear el archivo del agente |
| CORS error al conectar con API | Verifica que la API tenga CORS habilitado para localhost:4200 |
| Estilos no se aplican | Revisa que `angular.json` incluya Bootstrap y el tema CSS |
| Componentes no se renderizan | Verifica los imports en los componentes standalone |
| Error de HttpClient / conexión | Confirma que `apiUrl` en environment.ts coincida con el puerto de la API |
| ng serve falla | Ejecuta `npm install` para asegurar que las dependencias estén instaladas |

---

## 🔬 LABORATORIO 4: Pruebas y Documentación (20 min)

> **⚠️ PRERREQUISITO:** Este laboratorio requiere haber completado el **Laboratorio 2**. Necesitas:
> - El proyecto API Node.js con las interfaces y rutas creadas
> - Familiaridad con la estructura del proyecto

### Objetivos
- ✅ Generar pruebas unitarias automáticamente
- ✅ Usar el comando /tests
- ✅ Generar documentación JSDoc
- ✅ Crear README profesional

---

### Paso 4.1: Configurar Jest para pruebas

> **💡 NOTA:** Primero configuramos Jest como framework de pruebas para el proyecto Node.js.

**🤖 PROMPT en Modo Agent:**

```
Configura Jest para el proyecto API en src/api:

1. Instala las dependencias: jest, ts-jest, @types/jest, supertest, @types/supertest
2. Crea jest.config.ts con preset ts-jest
3. Agrega el script "test" en package.json: jest --verbose
4. Agrega el script "test:watch" en package.json: jest --watch
```

**📝 Alternativa manual:**

```bash
cd src/api
npm install -D jest ts-jest @types/jest supertest @types/supertest
```

---

### Paso 4.2: Generar pruebas unitarias con /tests

> **💡 COMANDO ESPECIAL:** El comando `/tests` genera automáticamente pruebas unitarias para el código seleccionado.

**📍 Cómo usar /tests:**
1. Abre el archivo `src/api/src/funcionalidades/polizas/poliza.model.ts`
2. Selecciona todo el contenido (Ctrl+A en el archivo)
3. Abre Copilot Chat y escribe el prompt

**🤖 PROMPT:**

```
/tests Genera pruebas unitarias completas para estas interfaces y funciones usando Jest.

Quiero pruebas que cubran:

1. La creación de objetos con datos válidos e inválidos (número de póliza vacío, nulo, fechas inconsistentes, montos negativos)

2. Los valores por defecto de las propiedades al crear una nueva instancia

3. Las funciones de validación y lógica de negocio

Requisitos generales:
- Patrón Arrange-Act-Assert con comentarios en español
- Nombres de métodos descriptivos que indiquen qué se prueba y qué se espera (describe/it en español)
- Usar test.each cuando haya múltiples casos similares
```

---

### Paso 4.3: Generar pruebas de integración

**🤖 PROMPT en Modo Agent:**

```
@workspace Crea pruebas de integración para los endpoints de pólizas usando Jest y Supertest.

Necesito pruebas que verifiquen el comportamiento completo de la API:

1. Pruebas para cada operación CRUD (obtener todos, obtener por id, crear, actualizar, eliminar)

2. Pruebas de casos de error (recurso no encontrado, datos inválidos)

3. Verificación de códigos de estado HTTP correctos para cada escenario

Configuración necesaria:
- Exportar la app Express por separado para pruebas (sin app.listen)
- Usar supertest(app) para realizar las peticiones
- Reiniciar datos en memoria antes de cada prueba con beforeEach
- Crear helpers para simplificar la creación de datos de prueba
```

---

### Paso 4.4: Generar documentación JSDoc con /doc

> **💡 COMANDO ESPECIAL:** El comando `/doc` genera documentación automáticamente.

**📍 Cómo usar /doc:**
1. Abre `src/api/src/funcionalidades/polizas/poliza.routes.ts`
2. Selecciona todo el contenido
3. Usa el comando /doc

**🤖 PROMPT:**

```
/doc Genera documentación JSDoc completa en español para estas rutas.

Para cada ruta y función incluye:
- Descripción clara de qué hace
- Documentación de todos los parámetros (@param)
- Descripción del valor de retorno (@returns)
- Códigos de respuesta HTTP posibles
- Anotaciones Swagger/OpenAPI (@swagger) para swagger-jsdoc

La documentación debe ser profesional, concisa y útil para que se muestre correctamente en Swagger UI
```

---

### Paso 4.5: Configurar Swagger con anotaciones JSDoc

**🤖 PROMPT en Modo Agent:**

```
@workspace Verifica y mejora la configuración de Swagger para que las rutas tengan documentación completa en la UI.

Necesito que:
- swagger-jsdoc esté configurado para leer los comentarios JSDoc de los archivos de rutas
- Cada endpoint tenga esquemas de request y response documentados
- Los modelos/interfaces aparezcan como componentes en Swagger
- La documentación esté en español
```

---

### Paso 4.6: Ejecutar pruebas

**🤖 PROMPT en Modo Agent:**

```
Ejecuta todas las pruebas del proyecto API y muéstrame los resultados
```

**📝 Alternativa manual:**

```bash
cd src/api
npm test
```

**✅ Verificar antes de continuar:**
- [ ] Todas las pruebas pasan (verde)
- [ ] Swagger muestra la documentación completa en /api-docs
- [ ] Los comentarios JSDoc aparecen en cada endpoint

---

### 🛠️ Troubleshooting Lab 4

| Problema | Solución |
|----------|----------|
| Jest no encuentra archivos | Verifica que `jest.config.ts` apunte al directorio correcto |
| Supertest error de conexión | Asegúrate de exportar `app` sin `app.listen()` para pruebas |
| Pruebas fallan por datos | Cada prueba debe reiniciar datos con `beforeEach` |
| Documentación Swagger no aparece | Verifica que swagger-jsdoc esté configurado para leer `*.routes.ts` |
| Error de tipos TypeScript en tests | Verifica que `@types/jest` y `@types/supertest` estén instalados |

---

## 🔬 LABORATORIO 5: Características Avanzadas (15 min)

> **⚠️ PRERREQUISITO:** Este laboratorio requiere haber completado los **Laboratorios 2 y 3**. Necesitas:
> - La estructura completa del proyecto API
> - El archivo `.github/copilot-instructions.md` configurado
> - Familiaridad con los modos de Copilot (Ask, Agent, Plan)

### Objetivos
- ✅ Traducir código legacy a TypeScript/Node.js moderno
- ✅ Integrar bibliotecas de terceros
- ✅ Crear agente de revisión de código

---

### Paso 5.1: Traducción de código legacy

> **💡 ESCENARIO:** Tienes código PHP antiguo de un sitio web de la CFE que muestra un contador de visitas. Necesitas migrarlo a Node.js/TypeScript moderno con Express.

**📝 Primero crea la carpeta y el archivo de ejemplo:**

```bash
mkdir legacy
```

**Luego crea el archivo:** `legacy/contador_visitas.php`

```php
<?php
// Código PHP legacy de ejemplo - Sitio web anterior de la CFE
// Contador de visitas de la página web

$archivo_contador = "contador.txt";

// Lee el número actual de visitas
function obtenerVisitas() {
    global $archivo_contador;
    if (file_exists($archivo_contador)) {
        $visitas = file_get_contents($archivo_contador);
        return intval($visitas);
    }
    return 0;
}

// Incrementa el contador y lo guarda
// NOTA: Este código tiene problemas de concurrencia (race condition)
function registrarVisita() {
    global $archivo_contador;
    $visitas = obtenerVisitas();
    $visitas++;
    file_put_contents($archivo_contador, $visitas);
    return $visitas;
}

// Obtiene visitas por página específica
// NOTA: Este código tiene vulnerabilidad de Path Traversal
function obtenerVisitasPorPagina($pagina) {
    $archivo = "contadores/" . $pagina . ".txt";
    if (file_exists($archivo)) {
        return intval(file_get_contents($archivo));
    }
    return 0;
}

// Registra visita para una página específica
// NOTA: Sin validación de entrada - vulnerable a inyección
function registrarVisitaPagina($pagina) {
    $archivo = "contadores/" . $pagina . ".txt";
    $visitas = obtenerVisitasPorPagina($pagina);
    $visitas++;
    file_put_contents($archivo, $visitas);
    return $visitas;
}

// Página principal
$total_visitas = registrarVisita();
$pagina_actual = isset($_GET['pagina']) ? $_GET['pagina'] : 'inicio';
$visitas_pagina = registrarVisitaPagina($pagina_actual);
?>

<html>
<head><title>CFE - Contador de Visitas</title></head>
<body>
    <h1>CFE</h1>
    <p>Total de visitas al sitio: <?php echo $total_visitas; ?></p>
    <p>Visitas a esta página (<?php echo $pagina_actual; ?>): <?php echo $visitas_pagina; ?></p>
    <p>Fecha: <?php echo date("d/m/Y H:i:s"); ?></p>
</body>
</html>
```

**🤖 PROMPT para traducir:**

```
Traduce este código PHP legacy a TypeScript moderno con Express siguiendo los estándares del proyecto CFE:

Requisitos de la traducción:

1. **Arquitectura**: Crear rutas Express
   - Crear visita.routes.ts en funcionalidades/visitas/
   - Crear visita.model.ts con: id, pagina, fechaVisita, direccionIp

2. **Modernización**:
   - Reemplazar archivos .txt por almacenamiento en memoria (Map<string, number>)
   - Convertir a async/await
   - Usar Map y arrays en lugar de file_get_contents/file_put_contents

3. **Seguridad** (CRÍTICO):
   - Corregir la vulnerabilidad de Path Traversal en obtenerVisitasPorPagina
   - Validar el parámetro "pagina" (solo alfanuméricos y guiones)
   - Sanitizar todas las entradas del usuario con express-validator o validación manual

4. **Endpoints**:
   - POST /api/v1/visitas/registrar?pagina=inicio (registra visita)
   - GET /api/v1/visitas/total (total de visitas del sitio)
   - GET /api/v1/visitas/:pagina (visitas por página)
   - GET /api/v1/visitas/resumen (resumen con visitas por página)

5. **Mejoras**:
   - Resolver el problema de concurrencia (race condition) usando operaciones atómicas
   - Agregar tipado estricto con TypeScript
   - Agregar manejo de errores robusto

6. **Documentación**:
   - JSDoc comments en español

Crea los archivos en src/api/src/funcionalidades/visitas/
```

---

### Paso 5.2: Integrar biblioteca externa

**🤖 PROMPT en Modo Plan:**

```
@workspace Quiero agregar funcionalidad para exportar reportes de pólizas a Excel.

Implementa lo siguiente:

1. **Paquete npm**: Agregar exceljs al proyecto API
   npm install exceljs

2. **Servicio de Exportación**: 
   Crear exportacion.servicio.ts en src/api/src/funcionalidades/exportacion/
   
   - Función: exportarPolizaAExcel(polizaId: string): Promise<Buffer>
   - Generar Excel con una hoja "Pólizas" con encabezados y datos
   - Formato básico: encabezados en azul (#003B71) con texto blanco

3. **Ruta Express**:
   GET /api/v1/polizas/:id/exportar
   - Retorna archivo Excel para descarga
   - Headers: Content-Type application/vnd.openxmlformats-officedocument.spreadsheetml.sheet
   - Content-Disposition: attachment; filename=poliza-{id}.xlsx

Muéstrame el plan primero
```

---

### Paso 5.3: Crear agente de revisión de código

**🤖 PROMPT en Modo Agent:**

```
Crea .github/agents/revisor-codigo.md con un agente especializado en revisión de código:

# Agente: Revisor de Código CFE (@revisor-codigo)

## Rol
Eres un revisor de código senior especializado en Node.js, TypeScript, Angular y los estándares de desarrollo de la CFE. Tu trabajo es revisar código y proporcionar retroalimentación constructiva.

## Idioma
Toda la retroalimentación debe estar en **español**.

## Checklist de Revisión

### Estándares del Proyecto
- [ ] Código en español (variables, funciones, comentarios)
- [ ] Estructura de carpetas por funcionalidad respetada
- [ ] Rutas Express implementadas correctamente
- [ ] Nombres siguen convenciones (camelCase funciones, PascalCase interfaces, kebab-case archivos)

### Calidad de Código
- [ ] Async/await usado correctamente
- [ ] Tipado TypeScript estricto (sin any innecesario)
- [ ] No hay código duplicado
- [ ] Funciones con responsabilidad única
- [ ] Complejidad ciclomática aceptable

### Seguridad
- [ ] Sin datos sensibles en logs
- [ ] Validación de entradas presente
- [ ] Sin inyecciones posibles (SQL, NoSQL, Path Traversal)
- [ ] Sin secretos hardcodeados

### Rendimiento
- [ ] Operaciones asíncronas optimizadas
- [ ] Sin bloqueo del event loop
- [ ] Paginación implementada en listas

### Documentación
- [ ] JSDoc en funciones y rutas públicas
- [ ] Comentarios útiles (no obvios)

### Pruebas
- [ ] Cobertura de casos principales
- [ ] Nombres descriptivos (describe/it)
- [ ] Arrange-Act-Assert

## Formato de Respuesta

Al revisar código, responde con este formato:

---

## 📋 Revisión de Código: [Nombre del archivo]

### ✅ Aspectos Positivos
- Punto positivo 1
- Punto positivo 2

### ⚠️ Sugerencias de Mejora (Opcionales)
| Línea | Sugerencia | Razón |
|-------|------------|-------|
| 15 | Cambiar X por Y | Mejora legibilidad |

### ❌ Problemas a Corregir (Obligatorios)
| Línea | Problema | Solución |
|-------|----------|----------|
| 23 | Falta validación | Agregar validación de entrada |

### 📝 Código Sugerido

(código corregido aquí)

### 📊 Resumen
- Calidad general: ⭐⭐⭐⭐☆ (4/5)
- Seguridad: ✅ Aprobado / ⚠️ Revisar / ❌ Rechazado
- Listo para merge: Sí / No / Con cambios menores

---

## Severidad de Problemas

- 🔴 **Crítico**: Bloquea merge (seguridad, errores graves)
- 🟠 **Mayor**: Debe corregirse antes de merge
- 🟡 **Menor**: Sugerencia de mejora
- 🟢 **Info**: Comentario informativo
```

---

### Paso 5.4: Usar el agente revisor

**🤖 PROMPT con Agente:**

```
@revisor-codigo Revisa el archivo src/api/src/funcionalidades/polizas/poliza.routes.ts

Evalúa:
1. Cumplimiento de estándares del proyecto CFE
2. Calidad y legibilidad del código
3. Posibles problemas de seguridad
4. Rendimiento de las operaciones
5. Completitud de la documentación
6. Cobertura de casos de error

Proporciona retroalimentación detallada con sugerencias de mejora específicas.
```

**✅ Verificar al finalizar el workshop:**
- [ ] Código legacy traducido compila sin errores
- [ ] El endpoint de exportación genera archivo Excel válido
- [ ] El agente @revisor-codigo proporciona feedback útil

---

### 🛠️ Troubleshooting Lab 5

| Problema | Solución |
|----------|----------|
| exceljs no instala | Verifica conexión a internet y ejecuta `npm install` |
| Error al generar Excel | Asegúrate de importar exceljs correctamente |
| Agente @revisor-codigo no funciona | Verifica la ruta `.github/agents/revisor-codigo.md` |
| Traducción de PHP incompleta | Proporciona más contexto en el prompt sobre los estándares |

---

## 📖 Referencia Rápida

### Comandos de Copilot Chat

| Comando | Descripción | Ejemplo |
|---------|-------------|---------|
| `@workspace` | Contexto del proyecto completo | `@workspace ¿cómo se implementan las rutas?` |
| `/tests` | Generar pruebas unitarias | Selecciona código → `/tests` |
| `/doc` | Generar documentación JSDoc | Selecciona función → `/doc` |
| `/fix` | Proponer corrección de errores | Selecciona error → `/fix` |
| `/explain` | Explicar código seleccionado | Selecciona código → `/explain` |
| `/new` | Crear nuevo archivo | `/new crear servicio de exportación` |
| `@frontend-cfe` | Agente de frontend | `@frontend-cfe crea componente` |
| `@revisor-codigo` | Agente de revisión | `@revisor-codigo revisa este archivo` |

### Atajos de Teclado

| Atajo | Acción |
|-------|--------|
| `Ctrl+I` | Abrir Copilot inline en el editor |
| `Ctrl+Shift+I` | Abrir panel de Copilot Chat |
| `Tab` | Aceptar sugerencia de Copilot |
| `Esc` | Rechazar sugerencia |
| `Alt+]` | Ver siguiente sugerencia |
| `Alt+[` | Ver sugerencia anterior |
| `Ctrl+Enter` | Abrir Copilot Completions Panel |

### Modos de Copilot

| Modo | Cuándo Usar |
|------|-------------|
| **Ask** 💬 | Explorar, entender, planificar (no modifica archivos) |
| **Agent** 🤖 | Implementar, crear archivos, hacer cambios |
| **Plan** 📋 | Tareas complejas multi-archivo (con aprobación) |

---

## ✅ Checklist Final del Workshop

Al terminar el workshop, deberías tener:

### Documentación
- [ ] `docs/especificaciones/especificacion-sistema.md`
- [ ] `docs/especificaciones/modelo-dominio.md`
- [ ] `docs/especificaciones/contratos-api.md`

### Backend (API Node.js)
- [ ] Proyecto Node.js + Express + TypeScript
- [ ] `funcionalidades/polizas/` completo (modelo, DTOs, rutas)
- [ ] `funcionalidades/vehiculos/` implementado
- [ ] `datos/almacen-datos.ts` configurado con datos semilla
- [ ] Swagger funcionando en `/api-docs`

### Frontend (Angular)
- [ ] Proyecto Angular con TypeScript
- [ ] Archivo SCSS con estilos institucionales CFE
- [ ] Layout principal (Header, Footer)
- [ ] Página de Inicio
- [ ] Página de Listado de Pólizas con CRUD
- [ ] Componentes reutilizables (TarjetaPoliza, etc.)
- [ ] Servicios Angular consumiendo la API de pólizas y vehículos

### Pruebas
- [ ] Pruebas unitarias con Jest para modelos
- [ ] Pruebas de integración con Supertest para endpoints

### Configuración de Copilot
- [ ] `.github/copilot-instructions.md`
- [ ] `.github/agents/frontend-cfe.md`
- [ ] `.github/agents/revisor-codigo.md`

### Extras
- [ ] Código legacy traducido a TypeScript moderno
- [ ] Servicio de exportación a Excel

---

## 📚 Recursos Adicionales

### Documentación Oficial
- [GitHub Copilot Docs](https://docs.github.com/en/copilot)
- [VS Code + Copilot](https://code.visualstudio.com/docs/copilot/overview)
- [Node.js Documentation](https://nodejs.org/docs/latest/api/)
- [Express.js Documentation](https://expressjs.com/)
- [Angular Documentation](https://angular.dev/)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [Bootstrap 5](https://getbootstrap.com/docs/5.3/)

### Patrones y Arquitectura
- [Express.js Best Practices](https://expressjs.com/en/advanced/best-practice-security.html)
- [Angular Style Guide](https://angular.dev/style-guide)
- [TypeScript Strict Mode](https://www.typescriptlang.org/tsconfig#strict)

### CFE
- [Portal CFE](https://www.cfe.mx/)
- [Seguros de Vehículos CFE](https://www.cfe.mx/seguros/)

---

## 🙋 Preguntas Frecuentes

### ¿Por qué Copilot no sigue mis instrucciones del archivo copilot-instructions.md?
Asegúrate de que:
1. El archivo esté en `.github/copilot-instructions.md`
2. Hayas recargado VS Code después de crearlo
3. Estés usando `@workspace` para que tome contexto

### ¿Cómo hago que Copilot genere código en español?
1. Configúralo en `.github/copilot-instructions.md` (Lab 2.1) — esto aplica para todo el proyecto
2. Proporciona ejemplos en español en tu código existente
3. Si aún no tienes `copilot-instructions.md`, agrega "Responde en español" al final del prompt como medida temporal

### ¿El Modo Plan no me muestra el plan, ¿qué hago?
- Verifica que tengas la última versión de la extensión
- Intenta con tareas más complejas (el plan es más útil para múltiples archivos)
- Usa Modo Agent si solo necesitas crear un archivo

### ¿Los agentes personalizados no funcionan?
- Verifica la ruta: `.github/agents/nombre-agente.md`
- El nombre del archivo (sin .md) es el nombre del agente
- Recarga VS Code después de crear el archivo

### ¿Por qué usamos almacenamiento en memoria?

Este taller usa arrays y Maps en memoria por las siguientes razones:

| Ventaja | Descripción |
|---------|-------------|
| **Sin instalación** | No requiere MongoDB, PostgreSQL ni ningún motor de BD |
| **Rápido** | Operaciones instantáneas, ideal para desarrollo |
| **Portable** | Funciona igual en cualquier máquina con Node.js |
| **Aislado** | Cada ejecución inicia limpia con datos semilla |

**Limitaciones a considerar:**
- Los datos se pierden al detener la aplicación
- No soporta consultas complejas como una BD real
- Para producción, cambiar a MongoDB, PostgreSQL u otra BD

**¿Cómo cambiar a MongoDB en producción?**
1. Instalar dependencias: `npm install mongoose`
2. Reemplazar almacén en memoria por modelos Mongoose
3. Agregar connection string en variables de entorno

**¿Cómo cambiar a PostgreSQL en producción?**
1. Instalar dependencias: `npm install pg typeorm`
2. Configurar TypeORM con entidades TypeScript
3. Agregar connection string en variables de entorno

---

## 👥 Créditos

**Workshop desarrollado para:** CFE (Comisión Federal de Electricidad de México)

**Tecnologías:** GitHub Copilot, Node.js, Express, Angular, TypeScript, Bootstrap

**Duración:** 3 horas

---

*¿Preguntas o comentarios? Contacta al equipo de capacitación.*
