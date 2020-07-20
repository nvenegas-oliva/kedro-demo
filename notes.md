# kedro - research

## Comments

- Se puede tener la configuración de acceso a las fuentes de datos encapsulada (`conf/local`).
- Workflow:
    - Set up project template.
    - Set up data.
    - Crear pipeline.
        - Crean los steps como funciones de python.
        - Se construye el pipeline agregando funciones como nodos.
        - Se configura cómo va a correr el pipeline, secuencial o paralelo.
    - Package project.
- Orientado a tener layers para los datos (`data/`):
```
data
├── 01_raw
│   └── iris.csv
├── 02_intermediate
├── 03_primary
├── 04_feature
├── 05_model_input
├── 06_models
├── 07_model_output
└── 08_reporting
```
- Se pueden correr los test utilizando un framework para esto (PyTest).
- Se puede ejecutar el pipeline utilizando threads (`runners`).
- Posee profilers.
- Para un proyecto pueden haber varios pipelines cada uno con muchos nodos.
- Se puede empaquetar para compartir el pipeline y la documentación pero sin los datos y las configuraciones.
- Se puede reproducir la historia del pipeline mediante los journals.

## Questions
- ¿Puedo utilizar kedro en el pipeline de entrenamiento y servirlo como API utilizando OTRO pipeline fuera de kedro?
