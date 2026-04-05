# CLAUDE.md

Este archivo orienta a Claude Code (claude.ai/code) para trabajar con este repositorio.

## Resumen del proyecto

Calculadora de Guardias: app HTML single-file que calcula bruto, neto e IRPF de guardias medicas. El usuario selecciona dias en calendarios interactivos, elige una configuracion hospitalaria y ve el desglose economico en tiempo real. Usa el Sistema de Diseno B ("Radiologia Glass") del proyecto COT padre.

## Desarrollo

```bash
# Servir en local (launch.json usa puerto 8080)
npx serve -l 8080

# Abrir en navegador
open http://localhost:8080
```

Sin build, sin dependencias, sin tests. Toda la app es `index.html` (~1700 lineas: CSS + HTML + JS).

## Arquitectura (index.html)

El archivo se estructura en tres bloques secuenciales:

1. **`<style>`** (~930 lineas) — variables CSS, glassmorphism, dark mode (`[data-theme="dark"]`), breakpoints responsive, grid de calendario, cajas de resultado
2. **`<body>`** (~30 lineas) — shell minimo: header, pills de configuracion, `#modules-grid`, `#final-card`, footer
3. **`<script>`** (~750 lineas) — toda la logica, organizada por cabeceras de seccion (`// ═══` y `// ───`)

### Secciones JS (en orden)

| Seccion | Linea | Proposito |
|---------|-------|-----------|
| Toast | ~964 | `mostrarToast()` notificacion |
| CONFIGS | ~980 | Objeto con 5 configuraciones hospitalarias, cada una con array `modules[]` |
| LOGOS | ~1019 | Rutas de logos dia/noche por hospital |
| Festivos | ~1029 | Calculo de festivos nacionales + autonomicos (algoritmo de Pascua, tablas CCAA) |
| Calendario | ~1126 | `renderCal()`, seleccion de dias (17h laborable / 24h finde+festivo), navegacion sincronizada |
| Renderizado modulos | ~1225 | `getModuleHTML()` genera HTML de card segun tipo: `presencial`, `compuesta`, `plana` |
| Tarjeta final | ~1341 | `renderFinalCard()` resumen con barras de desglose |
| `renderModules()` | ~1411 | Orquesta cambio de config: construye cards, bindea eventos, restaura tarifas |
| `calcular()` | ~1491 | Calculo principal: lee inputs, computa bruto/IRPF/neto por modulo + totales |
| Persistencia | ~1565 | `saveUserRates()` / `restoreUserRates()` / `saveConfig()` / `loadConfig()` via localStorage |
| Tema | ~1613 | Toggle oscuro/claro, deteccion automatica por hora, cambio de logos |
| Params URL | ~1672 | Acepta `?guardias=...` desde Planning COT para pre-rellenar guardias |
| Init | ~1696 | Bootstrap en `DOMContentLoaded` |

### Flujo de datos principal

```
CONFIGS[configKey].modules → renderModules() → getModuleHTML() por modulo
                                              → renderCal() por modulo (mes/ano compartido)
                                              → calcular() en cualquier cambio de input
```

### Tipos de modulo

Cada modulo en una config tiene un `type` que determina su estructura de tarifas y calculo:
- **`presencial`**: guardias x tarifa/h x horas (17h o 24h)
- **`compuesta`**: guardias x multiplicador x tarifa/h
- **`plana`**: guardias x tarifa/dia

### Estado

- `currentConfig` — clave de config activa (string)
- `calState[moduleId]` — `{year, month, selected: {dateKey: '17'|'24'}}` por calendario
- Claves localStorage: `calc_config`, `calc_rates_{configKey}`, `theme`

## Hosting

GitHub Pages en `jmacot.github.io/calculadora-guardias/`. Gate de autenticacion redirige al hub si falta el token `cot_auth` o esta expirado (linea 2).
