# ISR401-PFC-ERS-EQUIPO-I

Repositorio de la **Práctica Experimental 4 — Unidad IV** de Ingeniería de Requisitos (ISR-401):
validación, gestión de requisitos y herramientas CASE, aplicadas sobre la ERS del sistema
**SIMPA**.

- **Repositorio:** <https://github.com/equinteroj/ISR401-PFC-ERS-EQUIPO-I>
- **Línea base:** `baseline-v3.1` (ERS v3.1 / v1.1 de la rúbrica, aprobada por el CCB el 04-08-2026)
- **Institución:** Universidad Técnica Estatal de Quevedo — Facultad de Ciencias de la Computación
- **Asignatura / curso:** Ingeniería de Requerimientos — 4.º "A" Software
- **Docente:** Ing. Guerrero Ulloa Gleiston Cicerón, PhD.
- **Período:** 2026 PPA

> **Numeración de versiones.** La rúbrica designa el documento de la Entrega 2A como v1.0 y su
> revisión de esta práctica como v1.1; el historial interno del ERS las numera rev. 3.0 y
> rev. 3.1. Los archivos de `01_ERS/` usan la numeración de la rúbrica y el `CHANGELOG.md`
> declara ambas en cada entrada.

---

## 1. El sistema SIMPA

**SIMPA** (Sistema Inteligente de Mantenimiento de Palma Africana) es un sistema de gestión del
cultivo de palma africana con componentes de inteligencia artificial, desarrollado para
"Palmicultora M" (seudónimo), finca de aproximadamente 100 ha distribuidas en 6 lotes en el
cantón El Empalme, provincia del Guayas.

Alcance funcional del ERS:

- Gestión de la estructura productiva: autenticación, lotes, personal y variedades.
- Planificación de labores, registro de avance (incluido el registro delegado) y liquidación.
- Diagnóstico asistido por IA de plagas y deficiencias nutricionales a partir de imágenes, con
  modo de operación degradada sin inferencia remota (RF-40).
- Control de calidad y relación con la extractora (peso bruto/tara/neto, madurez, sobremadurez).
- Reportes, rastreo GPS de jornada y trazabilidad histórica.
- Cumplimiento de la LOPDP: consentimiento de geolocalización, derecho de eliminación y purga
  automática a los 12 meses (RD-11).

Contenido cuantitativo: 40 requisitos funcionales (39 + RF-40), 18 requisitos no funcionales
clasificados según ISO/IEC 25010:2023, 11 restricciones de diseño (10 + RD-11) y 8 requisitos
legales.

---

## 2. Integrantes

| Integrante | Roles en la PE4 | Rol en el CCB |
|---|---|---|
| Escudero Plaza María del Rosario | Moderadora e Inspector 2 (rol rotativo) de la inspección Fagan; repositorio Git y cierre de versión | Presidenta / voz del cliente |
| Huilcapi León Denisses Fabiola | Lectora de la inspección; redacción del ERS base y del backlog exportado | Analista y Secretaria (acta) |
| Quintero Gende Erick Jahir | Inspector 1; corrección de defectos; redacción de RFC y tablero Jira | Desarrollador y Verificador de la matriz |

El equipo está integrado por tres personas, por lo que uno de los integrantes asume además el
cuarto rol de la inspección Fagan (criterio A3 de la guía).

---

## 3. Estructura de carpetas

```
ISR401-PFC-ERS-EQUIPO-I/
├── README.md                          # Este archivo
├── CHANGELOG.md                       # Historial de versiones del ERS (v3.0 → v3.1)
│
├── 01_ERS/                            # Especificación de Requisitos del Software
│   ├── Fuentes_ERS_v1.1.tex           # Fuente LaTeX del ERS (archivo principal)
│   ├── ERS_v1.0.pdf                   # ERS de la Entrega 2A (rev. 3.0), insumo de la inspección
│   └── ERS_v1_1.pdf                   # ERS revisado tras el CCB (rev. 3.1) — línea base
│
├── 02_Inspeccion/                     # Inspección formal tipo Fagan
│   ├── AnexoA_checklists/             # Listas de verificación por inspector (Anexo A)
│   │   └── AnexoA_checklists.pdf
│   ├── AnexoB_registro_defectos.xlsx  # Registro consolidado de los 16 defectos
│   └── metricas.xlsx                  # Datos de las métricas y de las Figuras 1 a 3
│
├── 03_CCB/                            # Gestión del cambio
│   ├── RFC-01.pdf                     # Modo de operación degradada del componente de IA
│   ├── RFC-02.pdf                     # Política de concurrencia de RNF-11
│   ├── RFC-03.pdf                     # Plazo de retención de datos de geolocalización
│   ├── SOLI_RFC-01.pdf                # Formularios de solicitud firmados
│   ├── SOLI_RFC-02.pdf
│   ├── SOLI_RFC-03.pdf
│   └── Acta_CCB.pdf                   # Acta de la sesión del 04-08-2026
│
├── 04_Trazabilidad/                   # Herramienta CASE (Jira, proyecto SIM)
│   ├── backlog_export.csv             # Exportación del backlog (20 Stories + Sub-tasks)
│   └── capturas/                      # tablero_completo.png, SIM-*_detalle.png, panel_estadisticas.png
│
├── 05_Informe/                        # Informe de la PE4
│   ├── PE4_U4_ESCUDERO_HUILCAPI_QUINTERO.tex   # Archivo principal del informe
│   ├── referencias.bib                # Bibliografía IEEE (8 referencias)
│   ├── figures/                       # logo.png y gráficos de la inspección
│   └── PE4_U4_ESCUDERO_HUILCAPI_QUINTERO.pdf   # Entregable compilado
│
└── 06_Evidencias/                     # Evidencias complementarias
    ├── declaracion_IA.pdf             # Anexo F, firmado por los tres integrantes
    ├── capturas_git/                  # Capturas del historial y del tag de Git
    └── fotos_sesion/                  # Registro fotográfico de la sesión del CCB
```

---

## 4. Instrucciones de compilación

### 4.1 Informe de la PE4

**Archivo principal:** `05_Informe/PE4_U4_ESCUDERO_HUILCAPI_QUINTERO.tex`
**Compilador:** pdfLaTeX (TeX Live 2023 o posterior; MiKTeX 23.x o posterior).
No usar XeLaTeX ni LuaLaTeX: el documento emplea `inputenc`/`fontenc`.
**Bibliografía:** BibTeX sobre `referencias.bib`, estilo `IEEEtran`.

```bash
cd 05_Informe
pdflatex PE4_U4_ESCUDERO_HUILCAPI_QUINTERO.tex
bibtex   PE4_U4_ESCUDERO_HUILCAPI_QUINTERO
pdflatex PE4_U4_ESCUDERO_HUILCAPI_QUINTERO.tex
pdflatex PE4_U4_ESCUDERO_HUILCAPI_QUINTERO.tex
```

Las dos pasadas finales son obligatorias: la primera resuelve las citas y la segunda estabiliza
referencias cruzadas, numeración de cuadros y figuras y enlaces de `hyperref`.

Alternativa en un solo comando (ejecuta el ciclo completo):

```bash
cd 05_Informe
latexmk -pdf PE4_U4_ESCUDERO_HUILCAPI_QUINTERO.tex
```

Limpieza de auxiliares: `latexmk -c` (conserva el PDF) o `latexmk -C` (elimina también el PDF).

**Paquetes requeridos** (declarados en el preámbulo): `inputenc`, `fontenc`,
`babel` (opción `spanish`), `geometry`, `graphicx`, `longtable`, `booktabs`, `array`,
`tabularx`, `xcolor`, `colortbl`, `caption`, `enumitem`, `fancyhdr`, `titlesec`, `hyperref`.
Para la bibliografía se necesita además el estilo `IEEEtran.bst` (paquete `texlive-publishers`).

### 4.2 ERS

**Archivo principal:** `01_ERS/Fuentes_ERS_v1.1.tex`. Mismo ciclo:

```bash
cd 01_ERS
pdflatex Fuentes_ERS_v1.1.tex
bibtex   Fuentes_ERS_v1.1
pdflatex Fuentes_ERS_v1.1.tex
pdflatex Fuentes_ERS_v1.1.tex
```

Requiere, además de los anteriores: `amsmath`, `lastpage`, `url`, `hyphenat`, `adjustbox`.
La bibliografía usa `IEEEtran` con repliegue automático a `unsrt` si el estilo no está instalado.

### 4.3 Instalación de dependencias

```bash
sudo apt update
sudo apt install texlive-full latexmk        # Debian/Ubuntu
```

Con una instalación mínima, bastan `texlive-latex-recommended`,
`texlive-latex-extra`, `texlive-lang-spanish`, `texlive-publishers` y `latexmk`.

---

## 5. Línea base y control de versiones

```bash
git tag -a baseline-v3.1 -m "Baseline aprobada por CCB - Semana 14 - ERS SIMPA v3.1"
git push origin baseline-v3.1
```

Convención de mensajes de commit: `tipo(ámbito): descripción` (`docs`, `feat`, `chore`), con
ámbitos `ers`, `inspeccion`, `ccb`, `trazabilidad` y `repo`.

La versión declarada en la portada del ERS, en su historial de revisiones interno, en
`CHANGELOG.md` y en el tag de Git coinciden en **v3.1** (v1.1 de la rúbrica).

---

## 6. Clonación

```bash
git clone https://github.com/equinteroj/ISR401-PFC-ERS-EQUIPO-I.git
cd ISR401-PFC-ERS-EQUIPO-I
git checkout baseline-v3.1   # línea base aprobada por el CCB
```

