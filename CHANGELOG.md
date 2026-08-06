# Changelog

Historial de versiones de la ERS del sistema **SIMPA** en este repositorio.

Formato basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/).

> **Equivalencia de numeración.** La rúbrica de la asignatura designa el documento de la
> Entrega 2A como **v1.0** y su revisión de la PE4 como **v1.1**; el historial interno del ERS
> las numera como **rev. 3.0** y **rev. 3.1** respectivamente. Ambas se citan juntas en cada
> entrada. Los archivos del repositorio (`01_ERS/ERS_v1.0.pdf`, `01_ERS/ERS_v1_1.pdf`,
> `01_ERS/Fuentes_ERS_v1.1.tex`) usan la numeración de la rúbrica.

---

## [3.1] — v1.1 (rúbrica) — 2026-08-04

Versión resultante de la sesión del Change Control Board del 04-08-2026 (Semana 14).
Publicada como línea base `baseline-v3.1`.

### Añadido

- **RF-40** — Modo de operación degradada sin inferencia remota: el cliente móvil opera con los
  últimos umbrales de variedad y madurez sincronizados cuando el servicio de IA es inalcanzable
  por más de 4 horas continuas. Todo resultado obtenido en este modo se marca como "no
  verificado en línea". (**RFC-01**, aprobado con condiciones: se incorpora al ERS y a la matriz
  de trazabilidad, pero su implementación se difiere a la Entrega 4; no aplica al MVP vigente.)
- **RD-11** — Purga automática de los datos de geolocalización individual (marcaciones GPS y
  recorridos) a los 12 meses de su captura, conservando únicamente los agregados no
  identificables usados en RF-16. Se exceptúan los recorridos vinculados a una calificación
  desfavorable de la extractora hasta el cierre de la auditoría correspondiente.
  (**RFC-03**, aprobado.)
- **HU-20 / CA-20** — Historia de usuario y criterio de aceptación para el flujo alternativo B
  de CU-06 (clasificación de sobremadurez), previamente huérfano. (Defecto D-09.)
- **PT-01 a PT-16** — Casos de prueba asociados en la matriz de trazabilidad extendida.

### Cambiado

- **RD-05** — Reformulado para conciliarse con RD-02: se declara la dependencia de conectividad
  para la inferencia en línea y el repliegue a RF-40 ante indisponibilidad prolongada.
  (**RFC-01**; defecto crítico D-07.)
- **RNF-11** — Ampliado con política de concurrencia *last-write-wins* sobre el campo
  `fechaRegistro`, con bitácora de conflicto accesible al supervisor que efectuó el registro
  delegado (RF-35). (**RFC-02**, aprobado sin condiciones; defecto crítico D-12.)
- **RF-01** — Bloqueo de cuenta por 15 minutos tras 5 intentos fallidos consecutivos, con
  registro en bitácora de seguridad (RNF-13). (Defecto D-06.)
- **RF-23** — El registro inconsistente (bruto/tara/neto) pasa a estado *observado* y se
  notifica a la persona administradora. (Defecto D-01.)
- **RF-27 / RF-38** — Nueva postcondición sobre el tratamiento del remanente arrastrado cuando
  se ejecuta luego como labor no presupuestada. (Defecto D-02.)
- **RF-08 / CU-02** — Excepción E3 para imágenes con más de una deficiencia nutricional de
  confianza comparable. (Defecto D-04.)
- **RF-14 / CU-03** — Excepción E3 para la interrupción de la jornada de rastreo GPS por
  agotamiento de batería. (Defecto D-15.)
- **RL-03** — Plazo máximo de 60 segundos para propagar al backend la revocación del
  consentimiento de geolocalización. (Defecto D-08.)
- **§6.3 del ERS** — Se documenta RF-10 como bloqueante de RF-21 en el plan de la Entrega 4.
  (Defecto D-11.)
- **§7.5 del ERS** — Se incorpora la triangulación de evidencia para RF-11, RF-23, RF-25,
  RF-32, RF-33 y RF-34 antes del cierre de la Entrega 4. (Defecto crítico D-05.)

### Eliminado

- Ninguno.

### Pendiente justificado

- Defectos menores D-03, D-10, D-13 y D-14: diferidos a la Entrega 4 (2B) por requerir una
  decisión de negocio que excede el alcance de esta práctica; no comprometen la operación del
  MVP declarada en §6 del ERS.
- Defecto menor D-16: resuelto administrativamente (responsable: analista líder; plazo: cierre
  de la Entrega 4).

---

## [3.0] — v1.0 (rúbrica) — 2026-08-03

Versión de la Entrega 3 (2A), insumo de la inspección Fagan de esta práctica.
Archivo: `01_ERS/ERS_v1.0.pdf`.

### Añadido

- 39 requisitos funcionales, 18 requisitos no funcionales sobre ISO/IEC 25010:2023,
  10 restricciones de diseño y 8 requisitos legales (LOPDP).
- 19 historias de usuario en formato Connextra con criterios de aceptación en Gherkin.
- Matriz de trazabilidad extendida, diagramas UML, modelos i* y mockups MU-01 a MU-08.
- MVP en React/Vite.

### Cambiado

- Migración del documento a LaTeX.

### Eliminado

- Ninguno.

