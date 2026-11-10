# SIAMS Keep Alive

Este repositorio comprueba periódicamente la disponibilidad de [SIAMS](https://siams-unal.streamlit.app/) mediante GitHub Actions.

## Funcionamiento

El workflow `.github/workflows/keep_alive.yml` realiza una solicitud HTTPS cada 6 horas y también puede ejecutarse manualmente desde la pestaña **Actions**.

## Importante sobre Streamlit

Una solicitud HTTP exitosa no garantiza que Streamlit Community Cloud la considere una visita interactiva ni que evite la suspensión de la aplicación. El workflow sirve como comprobación de disponibilidad, pero la política de suspensión depende de Streamlit.

Si la aplicación sigue durmiéndose, la alternativa más fiable es automatizar un navegador real (por ejemplo, Playwright) que cargue la página y espere a que termine de iniciar. Eso consume más recursos y puede requerir un servicio de ejecución distinto de GitHub Actions.

## Archivos

- `.github/workflows/keep_alive.yml`: comprobación programada cada 6 horas.
- `README.md`: descripción y limitaciones.
