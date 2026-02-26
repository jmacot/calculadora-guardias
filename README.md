# 🏥 Calculadora de Guardias Medicas

Herramienta web para calcular la retribucion economica de las guardias medicas. Permite registrar guardias de presencia fisica y localizadas, visualizarlas en un calendario mensual y obtener automaticamente el importe bruto, IRPF y neto.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![Configuraciones](https://img.shields.io/badge/configuraciones-5-1a3a5c)
![Sin dependencias](https://img.shields.io/badge/dependencias-ninguna-grey)

---

## Acceso directo

[Abrir la aplicacion](https://jmacot.github.io/calculadora-guardias/)

No requiere instalacion. Funciona en cualquier navegador, incluyendo movil y tablet.

---

## Configuraciones predeterminadas

| Configuracion | Modulos |
|---|---|
| **HSJD** | Presenciales (GPF) + Localizadas HSJD |
| **HSJD + VITHAS** | Presenciales (GPF) + Localizadas HSJD + Localizadas Vithas |
| **VITHAS** | Localizadas Vithas |
| **SAS** | Presenciales SAS + Localizadas SAS (tarifas en blanco) |
| **SAS + PRIVADA** | Presenciales SAS + Localizadas SAS + Localizadas Privada (tarifas en blanco) |

---

## Funcionalidades

- **5 configuraciones predeterminadas**: HSJD, HSJD + VITHAS, VITHAS, SAS y SAS + PRIVADA
- **Modulos dinamicos**: cada configuracion muestra solo los modulos relevantes con sus tarifas
- **3 tipos de calculo**: presencial (guardias x tarifa/h x horas), compuesta (guardias x multiplicador x tarifa/h) y plana (guardias x tarifa/dia)
- **Calendario interactivo**: selecciona los dias de guardia directamente en el calendario. Todos los modulos se sincronizan al cambiar de mes
- **Calculo automatico**: obtiene al instante el importe bruto, la retencion de IRPF y el neto a percibir
- **Festivos nacionales y autonomicos**: detecta automaticamente festivos de todas las CCAA
- **Layout desktop 2 columnas**: los modulos se muestran lado a lado en pantallas grandes, con alineacion subgrid para que titulos, tarifas, calendarios y resultados queden a la misma altura
- **Integracion con Planning COT**: acepta parametros URL para pre-rellenar guardias desde el Analizador de Planning
- **Modo oscuro / modo claro**: cambia el tema con un solo clic, con deteccion automatica por hora y logos adaptados a cada modo
- **Persistencia**: guarda la configuracion seleccionada y las tarifas personalizadas en localStorage
- **Responsive**: adaptado para uso en escritorio, tablet y movil

---

## Como usar

1. Abre la aplicacion en el navegador
2. Selecciona la **configuracion** que corresponda a tu situacion laboral
3. Marca los dias de guardia en el **calendario** de cada modulo
4. Ajusta las **tarifas** si es necesario (las configuraciones SAS y Privada vienen en blanco)
5. Consulta el **desglose economico** en la parte inferior

---

## Estructura del proyecto

```
calculadora-guardias/
├── index.html        ← aplicacion principal
├── icon.png          ← icono de la app
├── imagenes/         ← logos de los centros en modo dia y noche
│   ├── hsjd-dia.jpg
│   ├── hsjd-noche.png
│   ├── vithas-dia.jpg
│   ├── vithas-noche.png
│   ├── sas-dia.png
│   └── sas-noche.png
├── .gitignore
├── LICENSE           ← MIT
└── README.md         ← este archivo
```

---

## Tecnologia

- **HTML5 + CSS3 + JavaScript vanilla**
- Tipografias: [Inter](https://fonts.google.com/specimen/Inter) y [Lora](https://fonts.google.com/specimen/Lora) (Google Fonts)
- Almacenamiento local (`localStorage`) para configuracion, tarifas y tema
- Sin frameworks, sin build tools, sin backend
- Compatible con Chrome, Firefox, Safari, Edge

---

## Licencia

MIT — Uso interno hospitalario.
