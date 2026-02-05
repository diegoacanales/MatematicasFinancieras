# Matemáticas Financieras (EC3004B)

Materiales del curso de Matemáticas Financieras · Tecnológico de Monterrey, Campus Puebla

## 🌐 Página del Curso

Visita la página del curso en: **https://diegoacanales.github.io/MatematicasFinancieras/**

## 📁 Estructura del Repositorio

```
MatematicasFinancieras/
├── sesion_01_beamer.tex   # Interés Simple e Interés Compuesto
├── sesion_02_beamer.tex   # Valor Presente y Descuento
├── sesion_03_beamer.tex   # Tasas Nominales, Efectivas y Equivalentes
├── sesion_04_beamer.tex   # Inflación y Tasas Reales
├── sesion_05_beamer.tex   # Anualidades Ordinarias (Vencidas)
├── sesion_06_beamer.tex   # Anualidades Anticipadas y Perpetuidades
├── sesion_07_beamer.tex   # Amortización de Préstamos
├── sesion_08_beamer.tex   # Valuación de Bonos
├── sesion_09_beamer.tex   # VPN y TIR
├── sesion_10_beamer.tex   # Valuación de Acciones e Integración
├── pdfs/                  # PDFs generados automáticamente
│   ├── sesion_01_beamer.pdf
│   ├── sesion_02_beamer.pdf
│   └── ...
├── _config.yml            # Configuración Jekyll
├── index.md               # Página principal del curso
└── assets/
    └── css/
        └── style.scss     # Estilos personalizados
```

## ⚙️ Compilación Automática

Los archivos `.tex` se compilan automáticamente a PDF cuando haces push a `main`:

1. GitHub Actions detecta cambios en archivos `.tex`
2. Compila todos los `.tex` usando `latexmk`
3. Guarda los PDFs en la carpeta `pdfs/`
4. Hace commit automático de los PDFs generados

También puedes disparar la compilación manualmente desde la pestaña "Actions" en GitHub.

## 🛠️ Desarrollo Local

### Compilar LaTeX localmente

```bash
cd modulo01
latexmk -pdf slides.tex
```

### Vista previa del sitio web

```bash
# Instalar Jekyll (una vez)
gem install bundler jekyll

# Servir localmente
bundle exec jekyll serve
```

Visita `http://localhost:4000` para ver el sitio.

## 📝 Agregar Nueva Sesión

1. Crea el archivo `sesion_XX_beamer.tex` en la raíz
2. Actualiza la tabla en `index.md`
3. Haz push a `main`

Los PDFs se generarán automáticamente en `pdfs/`.

## 👤 Contacto

**Diego A. Canales**  
Profesor de Economía · Tecnológico de Monterrey, Campus Puebla  
[diego.canales@tec.mx](mailto:diego.canales@tec.mx)

---

*Enfoque pedagógico: derivaciones desde primeros principios · cálculo mental · intuición financiera*
