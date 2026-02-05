# CLAUDE.md - Currículo de Matemáticas Financieras

## Descripción del Proyecto

Estás generando un currículo completo de **10 sesiones** sobre **Valor del Dinero en el Tiempo** para estudiantes de economía de pregrado con conocimientos básicos de álgebra. Cada sesión es una presentación Beamer en español de 1 hora 50 minutos.

---

## Estructura del Currículo Completo

### SEMANA 1: Fundamentos

| Sesión | Archivo | Título | Temas |
|--------|---------|--------|-------|
| 1 | `sesion_01_beamer.tex` | Interés Simple e Interés Compuesto | ✅ COMPLETADA |
| 2 | `sesion_02_beamer.tex` | Valor Presente y Descuento | • Derivación de VP: $P = F/(1+r)^n$ • Factor de descuento vs. capitalización • Tasa de descuento vs. tasa de interés • Diagramas de flujo de caja • Descuento simple vs. compuesto |

### SEMANA 2: Tasas y Equivalencias

| Sesión | Archivo | Título | Temas |
|--------|---------|--------|-------|
| 3 | `sesion_03_beamer.tex` | Tasas Nominales, Efectivas y Equivalentes | • Capitalización m veces al año • Tasa nominal vs. efectiva: $(1 + r_{ef}) = (1 + r_{nom}/m)^m$ • Tasa continua: $e^{r \cdot t}$ • Conversión entre tasas • APR vs. APY • **Puntos base y puntos porcentuales** |
| 4 | `sesion_04_beamer.tex` | Inflación y Tasas Reales | • Ecuación de Fisher: $(1+r_{real})(1+\pi) = (1+r_{nom})$ • Poder adquisitivo • Flujos nominales vs. reales • Indexación y ajuste por inflación |

### SEMANA 3: Anualidades

| Sesión | Archivo | Título | Temas |
|--------|---------|--------|-------|
| 5 | `sesion_05_beamer.tex` | Anualidades Ordinarias (Vencidas) | • Definición y diagramas temporales • Derivación VP: $PV = PMT \cdot \frac{1-(1+r)^{-n}}{r}$ • Derivación VF: $FV = PMT \cdot \frac{(1+r)^n - 1}{r}$ • Factor de anualidad • Fondos de ahorro |
| 6 | `sesion_06_beamer.tex` | Anualidades Anticipadas y Perpetuidades | • Anualidad anticipada: ajuste por $(1+r)$ • Perpetuidades: $PV = PMT/r$ • Perpetuidades crecientes: $PV = PMT/(r-g)$ • Aplicaciones: pensiones, rentas, dividendos |

### SEMANA 4: Préstamos y Bonos

| Sesión | Archivo | Título | Temas |
|--------|---------|--------|-------|
| 7 | `sesion_07_beamer.tex` | Amortización de Préstamos | • Sistema francés (cuota fija) • Sistema alemán (amortización constante) • Sistema americano (bullet) • Tablas de amortización • Saldo insoluto |
| 8 | `sesion_08_beamer.tex` | Valuación de Bonos | • **Estructura intertemporal de tasas (curva de rendimientos)** • **Interpolación lineal de tasas** • Anatomía del bono (cupón, principal, vencimiento) • Precio: $P = \sum \frac{C}{(1+r)^t} + \frac{F}{(1+r)^n}$ • Yield to Maturity (YTM) • Relación precio-rendimiento • Prima, par, descuento |

### SEMANA 5: Valuación de Proyectos

| Sesión | Archivo | Título | Temas |
|--------|---------|--------|-------|
| 9 | `sesion_09_beamer.tex` | VPN y TIR | • VPN: $VPN = \sum \frac{CF_t}{(1+r)^t} - I_0$ • Regla de decisión VPN • TIR y su cálculo • VPN vs. TIR: conflictos • TIR múltiple, proyectos excluyentes |
| 10 | `sesion_10_beamer.tex` | Valuación de Acciones e Integración | • Modelo de descuento de dividendos (DDM) • Modelo de Gordon: $P = D_1/(r-g)$ • Múltiplos (P/E, P/B) • **Caso integrador** • **Repaso general** |

---

## Especificaciones Técnicas del Beamer

### Preámbulo Estándar (copiar en cada sesión)

```latex
\documentclass[aspectratio=169,11pt]{beamer}

% TEMA Y COLORES
\usetheme{Madrid}
\usecolortheme{whale}

\definecolor{primaryblue}{RGB}{0,102,153}
\definecolor{accentgreen}{RGB}{0,128,0}
\definecolor{accentorange}{RGB}{204,102,0}
\definecolor{darkgray}{RGB}{64,64,64}

\setbeamercolor{palette primary}{bg=primaryblue,fg=white}
\setbeamercolor{palette secondary}{bg=primaryblue!80,fg=white}
\setbeamercolor{palette tertiary}{bg=primaryblue!60,fg=white}
\setbeamercolor{structure}{fg=primaryblue}
\setbeamercolor{block title}{bg=primaryblue,fg=white}
\setbeamercolor{block body}{bg=primaryblue!10}
\setbeamercolor{block title example}{bg=accentgreen,fg=white}
\setbeamercolor{block body example}{bg=accentgreen!10}
\setbeamercolor{block title alerted}{bg=accentorange,fg=white}
\setbeamercolor{block body alerted}{bg=accentorange!10}

% PAQUETES
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{amsmath,amssymb}
\usepackage{booktabs}
\usepackage{tikz}
\usepackage{pgfplots}
\usepackage{listings}
\usepackage{multicol}

\pgfplotsset{compat=1.17}

% CÓDIGO PYTHON
\lstdefinestyle{pythonstyle}{
    language=Python,
    basicstyle=\ttfamily\footnotesize,
    keywordstyle=\color{blue}\bfseries,
    stringstyle=\color{red},
    commentstyle=\color{accentgreen}\itshape,
    frame=single,
    breaklines=true,
    showstringspaces=false,
    backgroundcolor=\color{gray!10}
}

% NAVEGACIÓN Y PIE DE PÁGINA
\setbeamertemplate{navigation symbols}{}
\setbeamertemplate{footline}{
    \leavevmode%
    \hbox{%
        \begin{beamercolorbox}[wd=.333333\paperwidth,ht=2.25ex,dp=1ex,center]{author in head/foot}%
            \usebeamerfont{author in head/foot}Matemáticas Financieras
        \end{beamercolorbox}%
        \begin{beamercolorbox}[wd=.333333\paperwidth,ht=2.25ex,dp=1ex,center]{title in head/foot}%
            \usebeamerfont{title in head/foot}Sesión X  % <-- CAMBIAR NÚMERO
        \end{beamercolorbox}%
        \begin{beamercolorbox}[wd=.333333\paperwidth,ht=2.25ex,dp=1ex,right]{date in head/foot}%
            \usebeamerfont{date in head/foot}\insertframenumber{} / \inserttotalframenumber\hspace*{2ex}
        \end{beamercolorbox}}%
    \vskip0pt%
}
```

### Metadatos de Título (ajustar por sesión)

```latex
\title[Sesión N]{TÍTULO DE LA SESIÓN}
\subtitle{Subtítulo descriptivo}
\author{Matemáticas Financieras}
\institute{Valor del Dinero en el Tiempo}
\date{Semana X | Clase Y | Duración: 1h 50min}
```

---

## Estructura Obligatoria de Cada Sesión

Cada presentación DEBE incluir estas **8 secciones** en este orden:

### 1. Portada y Contenido (2 slides)
```latex
\begin{frame}
    \titlepage
\end{frame}

\begin{frame}{Contenido de la Sesión}
    \tableofcontents
\end{frame}
```

### 2. Introducción (~3-4 slides)
- Objetivos de aprendizaje (lista numerada)
- Conexión con sesión anterior (excepto Sesión 1)
- Motivación/pregunta inicial
- Definiciones clave

### 3. Derivaciones Matemáticas (~6-8 slides)
- Paso a paso con `\pause` para revelación progresiva
- Usar `align*` para ecuaciones
- Culminar en `\begin{block}{Fórmula de...}` con `\boxed{}`
- Incluir la intuición detrás de cada paso

### 4. Interpretación Geométrica/Visual (~2-3 slides)
- Gráficos TikZ/pgfplots
- Diagramas de flujo de caja cuando aplique
- Tablas comparativas

### 5. Trucos de Estimación Mental (~2-3 slides)
- Usar `\begin{alertblock}{}` para trucos
- Reglas prácticas (tipo "Regla del 72")
- Aproximaciones útiles
- Tabla de factores comunes para memorizar

### 6. Calculadora HP 12C (~3-4 slides)
- Recordatorio de teclas relevantes
- 2-3 ejemplos paso a paso en formato tabla:
```latex
\begin{tabular}{@{}lll@{}}
    \toprule
    \textbf{Teclas} & \textbf{Display} & \textbf{Descripción} \\
    \midrule
    ... & ... & ... \\
    \bottomrule
\end{tabular}
```
- Siempre recordar convención de signos (CHS)

### 7. Ejercicios Prácticos (~5-6 slides)
- **3-5 ejercicios** con soluciones completas
- Usar `\begin{block}{Problema}` para enunciado
- Mostrar solución con `\pause`
- Variar dificultad: fácil → intermedio → desafiante
- Incluir verificación con trucos mentales cuando sea posible

### 8. Python con numpy-financial (~2-3 slides)
- **1-2 ejercicios** de código
- Usar `\begin{lstlisting}[style=pythonstyle]`
- Mostrar salida esperada en `\begin{verbatim}`
- Funciones relevantes de `numpy-financial`:
  - `npf.fv()`, `npf.pv()`, `npf.rate()`, `npf.nper()`
  - `npf.pmt()`, `npf.ipmt()`, `npf.ppmt()` (para anualidades)
  - `npf.npv()`, `npf.irr()` (para VPN/TIR)

### 9. Resumen y Tarea (~2-3 slides)
- Resumen de fórmulas clave en dos columnas
- Lista de trucos/herramientas
- Tarea: 3-4 items incluyendo:
  - Ejercicios con HP 12C
  - Problema adicional desafiante
  - Código Python para ejecutar
  - Pregunta de reflexión

### 10. Cierre (1 slide)
```latex
\begin{frame}
    \begin{center}
        \Huge \textcolor{primaryblue}{\textbf{¿Preguntas?}}
        
        \vspace{1cm}
        \Large Próxima Sesión:\\
        \textbf{TÍTULO SIGUIENTE SESIÓN}
        
        \vspace{0.5cm}
        \normalsize Semana X, Clase Y
    \end{center}
\end{frame}
```

---

## Guía de Estilo

### Idioma
- **Todo en español** (excepto código Python que usa inglés para nombres de funciones)
- Usar terminología financiera estándar latinoamericana
- Términos técnicos: mantener siglas en inglés cuando son estándar (VPN, TIR, YTM, APR, APY)

### Notación Matemática Consistente
| Variable | Significado |
|----------|-------------|
| $P$ o $PV$ | Valor Presente / Principal |
| $F$ o $FV$ | Valor Futuro |
| $r$ o $i$ | Tasa de interés por período |
| $n$ | Número de períodos |
| $PMT$ | Pago periódico |
| $C$ | Cupón (en bonos) |
| $g$ | Tasa de crecimiento |
| $\pi$ | Tasa de inflación |
| $m$ | Frecuencia de capitalización |

### Formato de Números
- Usar `\$` para moneda: `\$1,000`
- Porcentajes: `10\%` o `0.10` según contexto
- Decimales con punto: `1.0823`

### Colores Semánticos
- **Azul (`primaryblue`)**: Fórmulas principales, definiciones
- **Verde (`accentgreen`)**: Ejemplos, verificaciones, tips
- **Naranja (`accentorange`)**: Alertas, trucos, advertencias importantes

### Uso de Bloques
```latex
\begin{block}{Título}           % Azul - Definiciones y fórmulas
\begin{exampleblock}{Título}    % Verde - Ejemplos y verificaciones  
\begin{alertblock}{Título}      % Naranja - Trucos y advertencias
```

---

## Conexiones Entre Sesiones

Al iniciar cada sesión (excepto la 1), incluir un slide de "Conexión con la Sesión Anterior":

| Sesión | Conectar con |
|--------|--------------|
| 2 | "En la sesión anterior vimos cómo el dinero crece hacia el futuro. Hoy aprenderemos el proceso inverso: traer el futuro al presente." |
| 3 | "Ya sabemos calcular VP y VF con una tasa. Pero ¿qué pasa cuando la capitalización no es anual?" |
| 4 | "Las tasas nominales y efectivas asumen dinero 'real'. ¿Qué pasa cuando consideramos la inflación?" |
| 5 | "Hasta ahora: flujos únicos. ¿Qué pasa con múltiples flujos iguales y periódicos?" |
| 6 | "Las anualidades ordinarias pagan al final. ¿Y si pagan al inicio? ¿Y si nunca terminan?" |
| 7 | "Aplicación práctica de anualidades: ¿cómo se estructuran los préstamos?" |
| 8 | "Los préstamos son deuda privada. Los bonos son deuda pública negociable." |
| 9 | "Valuamos bonos con flujos fijos. ¿Cómo evaluamos proyectos con flujos variables?" |
| 10 | "VPN y TIR para proyectos. ¿Y para acciones que pagan dividendos indefinidamente?" |

---

## Comandos de Compilación

```bash
# Compilar una sesión (ejecutar 2 veces para TOC)
cd /path/to/curriculum
pdflatex -interaction=nonstopmode sesion_XX_beamer.tex
pdflatex -interaction=nonstopmode sesion_XX_beamer.tex

# Verificar errores
grep -E "(Error|Warning|Overfull)" sesion_XX_beamer.log | head -20
```

---

## Checklist de Calidad por Sesión

Antes de entregar cada sesión, verificar:

- [ ] Compila sin errores
- [ ] TOC muestra todas las secciones
- [ ] ~40-50 slides totales
- [ ] Todas las 8 secciones presentes
- [ ] Mínimo 3 ejercicios a mano con soluciones
- [ ] Mínimo 1 ejercicio Python funcional
- [ ] Mínimo 2 ejemplos de HP 12C
- [ ] Mínimo 1 gráfico TikZ/pgfplots
- [ ] Fórmulas principales en `\boxed{}`
- [ ] Conexión con sesión anterior (si aplica)
- [ ] Preview de siguiente sesión
- [ ] Tarea asignada

---

## Progreso del Proyecto

- [x] Sesión 1: Interés Simple e Interés Compuesto
- [x] Sesión 2: Valor Presente y Descuento
- [x] Sesión 3: Tasas Nominales, Efectivas y Equivalentes (**incluye puntos base**)
- [x] Sesión 4: Inflación y Tasas Reales
- [x] Sesión 5: Anualidades Ordinarias (Vencidas)
- [x] Sesión 6: Anualidades Anticipadas y Perpetuidades
- [x] Sesión 7: Amortización de Préstamos
- [x] Sesión 8: Valuación de Bonos (**incluye curva de rendimientos e interpolación**)
- [x] Sesión 9: VPN y TIR
- [x] Sesión 10: Valuación de Acciones e Integración

**CURRÍCULO COMPLETADO** ✓

---

## Instrucción para Claude

Cuando el usuario pida generar una sesión específica:

1. **Lee este archivo completo** para contexto
2. **Usa el preámbulo estándar** exactamente como está
3. **Sigue la estructura de 8 secciones** obligatoria
4. **Revisa la tabla de temas** para el contenido específico
5. **Incluye la conexión** con la sesión anterior
6. **Genera ejercicios originales** (no repetir de otras sesiones)
7. **Compila y verifica** que no hay errores
8. **Actualiza el progreso** en este archivo

Para generar la siguiente sesión, el usuario solo necesita decir:
> "Genera la Sesión N"

Y Claude producirá el archivo `.tex` completo siguiendo todas estas especificaciones.
