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
- Es extensible mediante hook, ejemplo:
    - Trackear métricas de ML utilizando MLFLow.
    - Validar datos antes que los nodos sean ejecutados con Great-Expectations.
- Tipos de Hooks
    - `after_catalog_created`
    - `before_node_run`
    - `after_node_run`
    - `on_node_error`
    - `before_pipeline_run`
    - `after_pipeline_run`
    - `on_pipeline_error`

## Questions
- ¿Puedo utilizar kedro en el pipeline de entrenamiento y servirlo como API utilizando OTRO pipeline fuera de kedro?

## Reading
- [Cuándo se podría deployar en kubeflow?](https://github.com/quantumblacklabs/kedro/issues/353).
- [Intro a kedro](https://medium.com/quantumblack/introducing-kedro-the-open-source-library-for-production-ready-machine-learning-code-d1c6d26ce2cf).
- [documentación oficial de Kedro](https://kedro.readthedocs.io/en/stable/).
- [Extender Kedro](https://medium.com/quantumblack/deploying-and-versioning-data-pipelines-at-scale-942b1d81b5f5).
- [Kedro Workflow](https://towardsdatascience.com/kedro-prepare-to-pimp-your-pipeline-f8f68c263466).
