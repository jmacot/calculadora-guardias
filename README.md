# 🏥 Calculadora de Guardias Médicas

Herramienta web para calcular la retribución económica de las guardias médicas. Permite registrar guardias de presencia física y localizadas, visualizarlas en un calendario mensual y obtener automáticamente el importe bruto, IRPF y neto.

---

## ✨ Funcionalidades

- **Tres módulos de guardia**: Guardias de Presencia Física (GPF), Guardias HSJD y Guardias Localizadas (Vithas)
- **Calendario interactivo**: Selecciona los días de guardia directamente en el calendario. Los tres módulos se sincronizan al cambiar de mes
- **Cálculo automático**: Introduce el valor de cada guardia y obtiene al instante el importe bruto, la retención de IRPF y el neto a percibir
- **Modo oscuro / modo claro**: Cambia el tema con un solo clic, con logos adaptados a cada modo
- **Sin instalación**: Es un único archivo HTML autocontenido. Ábrelo en cualquier navegador

---

## 🚀 Uso

1. Descarga o clona el repositorio
2. Abre el archivo `index.html` en tu navegador
3. Selecciona el mes y el año
4. Marca los días de guardia en el calendario de cada módulo
5. Introduce el valor económico de cada tipo de guardia
6. Consulta el desglose económico en la parte inferior

---

## 📁 Estructura

```
calculadora-guardias/
├── index.html        # Aplicación completa (HTML + CSS + JS)
└── imagenes/         # Logos de los centros en modo día y noche
    ├── hsjd-dia.png
    ├── hsjd-noche.png
    ├── vithas-dia.png
    └── vithas-noche.png
```

---

## 🛠️ Tecnología

- HTML5, CSS3 y JavaScript puro (sin frameworks ni dependencias externas)
- Almacenamiento local (`localStorage`) para recordar la preferencia de tema entre sesiones

---

## 📄 Licencia

Uso personal. Desarrollado para gestión interna de guardias médicas.
