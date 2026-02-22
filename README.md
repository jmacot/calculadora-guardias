# 🏥 Calculadora de Guardias Medicas

Herramienta web para calcular la retribucion economica de las guardias medicas. Permite registrar guardias de presencia fisica y localizadas, visualizarlas en un calendario mensual y obtener automaticamente el importe bruto, IRPF y neto.

![HTML5](https://img.shields.io/badge/HTML5-single--file-E34F26?logo=html5&logoColor=white)
![Modulos](https://img.shields.io/badge/modulos-3-1a3a5c)
![Sin dependencias](https://img.shields.io/badge/dependencias-ninguna-grey)

---

## Acceso directo

[Abrir la aplicacion](https://jmacot.github.io/calculadora-guardias/)

No requiere instalacion. Funciona en cualquier navegador, incluyendo movil y tablet.

---

## Funcionalidades

- **Tres modulos de guardia**: Guardias de Presencia Fisica (GPF), Guardias HSJD y Guardias Localizadas (Vithas)
- **Calendario interactivo**: selecciona los dias de guardia directamente en el calendario. Los tres modulos se sincronizan al cambiar de mes
- **Calculo automatico**: introduce el valor de cada guardia y obtiene al instante el importe bruto, la retencion de IRPF y el neto a percibir
- **Modo oscuro / modo claro**: cambia el tema con un solo clic, con deteccion automatica por hora y logos adaptados a cada modo
- **Responsive**: adaptado para uso en escritorio, tablet y movil

---

## Como usar

1. Abre la aplicacion en el navegador
2. Selecciona el **mes** y el **ano**
3. Marca los dias de guardia en el **calendario** de cada modulo
4. Introduce el **valor economico** de cada tipo de guardia
5. Consulta el **desglose economico** en la parte inferior

---

## Estructura del proyecto

```
calculadora-guardias/
├── index.html        ← aplicacion completa (archivo unico)
├── icon.png          ← icono de la app
├── imagenes/         ← logos de los centros en modo dia y noche
│   ├── hsjd-dia.png
│   ├── hsjd-noche.png
│   ├── vithas-dia.png
│   └── vithas-noche.png
├── .gitignore
├── LICENSE           ← MIT
└── README.md         ← este archivo
```

---

## Tecnologia

- **HTML5 + CSS3 + JavaScript vanilla** en archivo unico
- Tipografias: [Inter](https://fonts.google.com/specimen/Inter) y [Lora](https://fonts.google.com/specimen/Lora) (Google Fonts)
- Almacenamiento local (`localStorage`) para preferencia de tema
- Sin frameworks, sin build tools, sin backend
- Compatible con Chrome, Firefox, Safari, Edge

---

## Licencia

MIT — Uso interno hospitalario.
