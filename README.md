# CatStudyAI Frontend

Cliente web independiente del MVP academico, pensado para carga de material, chat con contexto RAG, generacion de evaluaciones y visualizacion de progreso.

## Proposito

Este repositorio concentra la experiencia de usuario: navegacion, composicion visual, estado de pantalla y comunicacion con la API del backend.

## Enfoque de arquitectura

La base sigue una arquitectura por features sobre Next.js + TypeScript. El frontend consume endpoints REST autenticados por JWT y prioriza separacion entre UI, logica de casos de uso y acceso a datos.

## Patrones aplicados

- Adapter: traduce respuestas del backend a modelos de interfaz.
- Facade: simplifica operaciones complejas por feature.
- Strategy: permite variantes de comportamiento segun flujo o estado.
- Container and Presentational: separa coordinacion de datos y renderizado.

## Justificacion

El frontend tendra flujos asincronos distintos y multiples modulos funcionales. Organizar por features permite escalar sin mezclar responsabilidades y mejora mantenibilidad.

## Git Flow recomendado

Se adopta Git Flow para tener releases previsibles y trabajo paralelo sin bloquear al equipo.

- `main`: versiones aprobadas para despliegue.
- `develop`: integracion funcional continua.
- `feature/*`: implementacion de capacidades nuevas.
- `release/*`: estabilizacion y validacion previa a entrega.
- `hotfix/*`: solucion urgente en produccion.

## Estructura actual

- `app/`: enrutado y capa de pagina.
- `components/`: componentes reutilizables.
- `features/`: modulos funcionales.
- `features/auth/`: autenticacion y sesion.
- `features/dashboard/`: metricas y progreso.
- `features/rooms/`: gestion de salas de estudio.
- `features/documents/`: carga y estado de documentos.
- `features/chat/`: interfaz de consulta RAG.
- `features/quizzes/`: evaluaciones y resultados.
- `hooks/`: hooks compartidos.
- `lib/`: utilidades de integracion.
- `lib/api/`: cliente API y normalizacion de respuestas.
- `lib/auth/`: helpers de autenticacion.
- `types/`: contratos tipados.
- `public/`: recursos estaticos.

## Archivos init

Se usan archivos `init.ts` y `init.txt` como placeholders para mantener la estructura visible en GitHub durante la fase de prototipo.

## Flujo recomendado

1. `lib/api` obtiene datos y maneja errores de transporte.
2. `features/*` organiza logica de caso de uso por dominio.
3. `components/*` renderiza vistas desacopladas de la capa de red.
4. `hooks/*` encapsula comportamiento reutilizable.

## Por qué GitFlow

Se usa Git Flow para evitar mezclar trabajo incompleto en ramas estables. Este esquema separa exploración, integración y salida a producción, y ayuda a mantener controlados los cambios del frontend mientras crece por features.

- `main`: versión estable lista para release.
- `develop`: integración continua del trabajo aprobado.
- `feature/*`: desarrollo aislado por funcionalidad.
- `release/*`: estabilización previa a entrega.
- `hotfix/*`: correcciones urgentes sobre producción.

## Convenciones tecnicas

- Evitar logica de negocio dentro de componentes visuales.
- Mantener estado global al minimo necesario.
- Centralizar acceso HTTP en `lib/api`.
- Crecer por modulos de `features` sin acoplar pantallas entre si.

