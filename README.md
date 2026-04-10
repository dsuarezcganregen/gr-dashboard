# Dashboard — Agencia Digital Ganadería Regenerativa

Tablero de métricas y análisis estratégico de las redes sociales de GanaderíaRegenerativa.com.

## Estructura del repositorio

```
gr-dashboard/
├── index.html              ← Dashboard principal
├── data/
│   └── dashboard-data.json ← Base de datos (se actualiza semanalmente)
└── README.md
```

## Configuración inicial (una sola vez)

### 1. Crear el repositorio en GitHub

1. Ve a https://github.com/new
2. Nombre del repositorio: `gr-dashboard`
3. Visibilidad: **Public** (necesario para GitHub Pages gratuito)
4. Marca "Add a README file"
5. Clic en **Create repository**

### 2. Subir los archivos

1. En el repositorio recién creado, clic en **Add file → Upload files**
2. Arrastra los archivos: `index.html` y la carpeta `data/` con `dashboard-data.json`
3. Clic en **Commit changes**

### 3. Activar GitHub Pages

1. En el repositorio, ve a **Settings → Pages**
2. En "Source", selecciona **Deploy from a branch**
3. Branch: **main**, carpeta: **/ (root)**
4. Clic en **Save**
5. En 1-2 minutos tu dashboard estará en: `https://TU-USUARIO.github.io/gr-dashboard/`

## Actualización semanal (flujo con Google Drive)

### Cómo funciona

1. Analizas tus métricas en el proyecto de Claude
2. Claude genera el `dashboard-data.json` actualizado
3. Claude guarda el archivo en tu Google Drive
4. Tú descargas de Drive y subes a GitHub (o configuras automatización)

### Opción manual (2 minutos)

1. Descarga `dashboard-data.json` desde Google Drive
2. En GitHub, navega a `data/dashboard-data.json`
3. Clic en el ícono de lápiz (editar)
4. Selecciona todo el contenido y reemplázalo con el nuevo JSON
5. Clic en **Commit changes**
6. GitHub Pages se actualiza automáticamente en ~1 minuto

### Opción automatizada (futura con Claude Code)

Cuando migres a Claude Code, el flujo será:
```bash
# Claude Code ejecutará esto automáticamente
cd gr-dashboard
cp ~/dashboard-data.json data/dashboard-data.json
git add data/dashboard-data.json
git commit -m "Actualización semana YYYY-WXX"
git push origin main
```

## Estructura del JSON

El archivo `dashboard-data.json` tiene esta estructura:

- `meta`: Información del proyecto y fecha de última actualización
- `semanas[]`: Array de objetos, uno por semana analizada
  - `id`: Identificador de semana (formato ISO: "2026-W14")
  - `fecha_inicio` / `fecha_fin`: Rango de fechas
  - `plataformas`: Objeto con datos de Instagram, Facebook, YouTube, TikTok
  - `top_contenidos[]`: Los mejores posts de la semana
  - `diagnostico`: Resumen, hallazgos y acciones recomendadas por la agencia
- `contenidos[]`: Registro histórico de todos los contenidos analizados

## Acceso del equipo

Comparte la URL de GitHub Pages con tu equipo. No necesitan cuenta de GitHub ni de Claude para ver el dashboard. Solo un navegador.

## Soporte

Este dashboard es generado y mantenido por la Agencia Digital GR dentro del proyecto de Claude. Cualquier ajuste al diseño o estructura se hace desde ahí.
