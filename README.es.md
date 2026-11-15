# EduTrack — Auditoría de Bases de Datos SQL y Análisis de Datos

Proyecto práctico de auditoría de bases de datos SQL centrado en la calidad de los datos, la gestión de registros y la obtención de información relevante para un negocio de formación online.

[English](README.md) | [Español](README.es.md)

## Descripción general

EduTrack es una plataforma ficticia de aprendizaje online que sirve como contexto para un ejercicio de auditoría de bases de datos.

La plataforma llevaba dos años operando y recopilaba registros de inscripciones a través de distintos canales sin haber realizado una revisión formal de la calidad de sus datos.

El objetivo de este proyecto fue auditar su base de datos de inscripciones, identificar inconsistencias, corregir registros incompletos, eliminar cuentas de prueba y extraer información relevante para apoyar los informes operativos.

El proyecto utiliza consultas SQL ejecutadas en Supabase y documenta los resultados reales en un informe de análisis específico.

## Objetivos del proyecto

- Identificar estudiantes con porcentajes bajos de finalización de cursos y posibles casos de abandono.
- Detectar registros de inscripciones sin información del instructor.
- Insertar un registro de inscripción faltante.
- Eliminar cuentas de prueba y sus inscripciones asociadas.
- Analizar la distribución de inscripciones por categoría de curso.
- Calcular los porcentajes medios de finalización de los cursos.
- Identificar los cursos con mayor volumen de inscripciones.
- Agrupar los importes abonados por categoría de curso.
- Documentar los resultados y hallazgos de las consultas en un informe legible.

## Funcionalidades principales

### Consulta y filtrado de datos

- Consultar registros de inscripciones por curso.
- Identificar estudiantes con porcentajes de finalización inferiores al 10%.
- Encontrar registros sin asignación de instructor.
- Clasificar estudiantes según su progreso entre aquellos que no han aprobado.
- Filtrar registros de inscripciones por fecha.

### Modificación y limpieza de datos

- Insertar un registro de inscripción faltante mediante `INSERT`.
- Actualizar registros sin información del instructor mediante `UPDATE`.
- Eliminar inscripciones de cuentas de prueba mediante `DELETE`.
- Verificar los registros antes y después de las modificaciones.

### Agregación y análisis de datos

- Contabilizar inscripciones por categoría mediante `COUNT()` y `GROUP BY`.
- Calcular porcentajes medios de finalización mediante `AVG()`.
- Filtrar resultados agrupados mediante `HAVING`.
- Calcular los importes totales abonados por categoría mediante `SUM()`.
- Ordenar los resultados agregados para facilitar las comparaciones.

## Stack tecnológico

| Tecnología | Uso |
|---|---|
| SQL | Consultas, auditoría y manipulación de datos |
| PostgreSQL | Motor de base de datos relacional |
| Supabase | Alojamiento de la base de datos y ejecución de consultas SQL |
| Markdown | Documentación técnica e informes de análisis |
| GitHub | Control de versiones y documentación del proyecto |

## Estructura del repositorio

```text
aie-pt-3--auditoria-datos-edutrack/
│
├── README.md
├── README.es.md
├── queries.sql
├── analysis_report.md
│
├── Comprobación courses.png
├── Comprobación inicial.png
├── Comprobación students.png
└── Ejecución exitosa de base de datos de Edutrack.png
```

## Consultas SQL

El archivo `queries.sql` contiene 12 ejercicios principales que abarcan diferentes operaciones de bases de datos:

| # | Operación | Conceptos SQL |
|---|---|---|
| 01 | Consultar inscripciones de un curso específico | `SELECT`, `WHERE` |
| 02 | Identificar posibles abandonos | Filtrado |
| 03 | Encontrar inscripciones sin instructor | `IS NULL` |
| 04 | Clasificar estudiantes que no han aprobado | `ORDER BY`, `LIMIT` |
| 05 | Consultar inscripciones del último año | Filtrado por fechas, subconsultas |
| 06 | Insertar una inscripción faltante | `INSERT INTO` |
| 07 | Asignar un valor por defecto a instructores faltantes | `UPDATE` |
| 08 | Eliminar inscripciones de cuentas de prueba | `DELETE`, `LIKE` |
| 09 | Contabilizar inscripciones por categoría | `COUNT()`, `GROUP BY` |
| 10 | Calcular el promedio de finalización por curso | `AVG()`, `GROUP BY` |
| 11 | Identificar cursos con más de tres inscripciones | `HAVING` |
| 12 | Calcular los importes abonados por categoría | `SUM()`, `GROUP BY` |

**Nota:** El análisis de fechas incluye una consulta alternativa que utiliza la fecha de inscripción más reciente del conjunto de datos como punto de referencia. Esto fue necesario porque la consulta original basada en la fecha actual no devolvía registros con los datos históricos disponibles.

## Informe de análisis

El archivo `analysis_report.md` documenta los resultados reales de las consultas, incluyendo:

- Estudiantes con porcentajes bajos de finalización de cursos.
- Registros de inscripciones que requieren asignación de instructor.
- Registros insertados, actualizados y eliminados correctamente.
- Distribución de inscripciones por categoría.
- Porcentajes medios de finalización por curso.
- Cursos con más de tres inscripciones.
- Importes abonados agrupados por categoría.

El informe permite consultar los hallazgos sin necesidad de ejecutar las consultas SQL.

## Ejecución y validación de la base de datos

Las consultas SQL se ejecutaron utilizando el editor SQL de Supabase.

Se realizaron comprobaciones iniciales para verificar la disponibilidad y estructura de las tablas `enrollments`, `students` y `courses`.

El repositorio incluye capturas de pantalla que documentan las comprobaciones iniciales y la ejecución correcta de la base de datos.

## Cómo empezar

Este repositorio contiene las consultas SQL y la documentación del análisis. No incluye el script original de creación de la base de datos ni un conjunto de datos completo.

Para reproducir el análisis:

1. Crear o acceder a un proyecto de Supabase.
2. Configurar la base de datos EduTrack con las tablas y los registros de origen necesarios.
3. Abrir el editor SQL de Supabase.
4. Revisar y ejecutar las consultas de `queries.sql` sobre la base de datos preparada.
5. Comparar los resultados con los hallazgos documentados en `analysis_report.md`.

**Importante:** Las instrucciones `INSERT`, `UPDATE` y `DELETE` modifican los registros de la base de datos. Ejecutarlas sobre una base de datos de pruebas adecuada y revisar los registros afectados antes de ejecutarlas.

## Alcance del proyecto

Este proyecto se centra en habilidades prácticas de SQL y auditoría de bases de datos relacionales, no en el desarrollo de aplicaciones.

Demuestra el uso de SQL para investigar problemas de calidad de datos, realizar modificaciones controladas, generar resultados agregados y comunicar los hallazgos mediante documentación técnica.

---

**Developer Wendy Sanchez**
