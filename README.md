## ¿Por qué uv?

Python solía requerir varias herramientas para configurar un proyecto. `uv` las reemplaza todas en una sola herramienta.

El beneficio principal es la consistencia. `uv` genera un archivo `uv.lock` que registra la versión exacta de cada paquete instalado — así cada máquina, cada ejecución de CI (tests automáticos que corren en la nube), y cada despliegue (cuando subes tu app a un servidor) funciona desde el mismo entorno exacto. Se acabó el "en mi ordenador funciona...".

Cada `uv add` o `uv remove` actualiza automáticamente `pyproject.toml`, resuelve las dependencias y reescribe el lockfile en un solo paso, sin ediciones manuales.

## ¿Qué es?

`uv` es un gestor de dependencias de Python escrito en Rust, lo que lo hace mucho más rápido que `pip`.

Gestiona todo: la versión de Python del proyecto, el entorno virtual, y las dependencias (los paquetes externos que tu código necesita para funcionar).

## Instalación

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## Comandos básicos

**Inicializar un nuevo proyecto y crear un entorno virtual:**
```bash
uv init
```

**Añadir un paquete nuevo:**
```bash
uv add <nombre-del-paquete>
```

**Eliminar un paquete:**
```bash
uv remove <nombre-del-paquete>
```

**Ejecutar un script o comando dentro del entorno:**
```bash
uv run python main.py
uv run pytest
```

`uv run` ejecuta cualquier cosa dentro del entorno del proyecto, verificando automáticamente que está sincronizado con el lockfile antes de ejecutar.

## Artículos interesantes

- [uv — Repositorio oficial](https://github.com/astral-sh/uv) — El código fuente y la documentación completa de uv, por Astral. Buena referencia para funcionalidades avanzadas, changelogs y benchmarks.
- [Python dependencies with uv](https://vladfilippov.com/python-dependencies-with-uv/) — Guía práctica del flujo de trabajo diario con uv, que cubre desde añadir dependencias hasta integración con CI/CD y despliegue.
- [uv: A Guide to Python Package Management](https://flocode.substack.com/p/044-python-environments-again-uv) — Introducción a uv para principiantes orientada a flujos de trabajo de datos e ingeniería, con foco en VS Code y Jupyter Notebooks.
- [Production-ready Python Docker Containers with uv](https://hynek.me/articles/docker-uv/) — Guía avanzada para construir contenedores Docker optimizados con uv, cubriendo builds multi-stage, layer caching y buenas prácticas de producción.
