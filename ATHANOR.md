# AT-GRCA · CISO Assistant Community con la apariencia de Athanor Tech

Este repositorio es una copia de [CISO Assistant Community](https://github.com/intuitem/ciso-assistant-community), de **intuitem**, publicada bajo la licencia **AGPL-3.0** (ver `LICENSE-AGPL.txt` y `LICENSE.md`). Athanor Tech lo usa en su servicio AT-GRCA y publica aquí sus cambios, como pide la licencia.

**No es el producto oficial de intuitem.** «CISO Assistant» e «intuitem» son marcas de sus dueños.

## Qué cambia Athanor Tech

Solo la apariencia del frontend. El backend se usa sin cambios, con la imagen oficial de intuitem. No se usa ni se modifica nada de la carpeta `enterprise/`, que tiene otra licencia.

| Archivo | Cambio |
|---|---|
| `frontend/src/athanor-theme.css` (nuevo) | Colores de Athanor Tech: azul #0048A8 como primario y naranja #E34B1D como acento; los morados y rosados fijos pasan a tonos de azul, y el fucsia al naranja. |
| `frontend/src/app.css` | Una línea que carga `athanor-theme.css` después del tema de CISO Assistant. |
| `frontend/src/lib/components/Logo/Logo.svelte` | Muestra el logo de Athanor Tech (versión clara y para modo oscuro). |
| `frontend/src/lib/assets/athanor-logo.png`, `athanor-logo-oscuro.png` (nuevos) | El logo. |
| `frontend/static/favicon.ico`, `frontend/src/lib/assets/favicon.ico` | El ícono del navegador. |
| `frontend/messages/es.json`, `en.json` | Saludo del ingreso (at.4): «Te damos la bienvenida a AT-GRCA. Gobierno, riesgo y cumplimiento, **en un solo lugar.**»; «Acerca de AT-GRCA»; dos textos nuevos para el pie del ingreso (`atgrcaPoweredBy`, `atgrcaSourceCode`). En `es.json` (at.3): «Catálogo» en vez de «Catalogar», «requisitos no conformes», «Respuestas» (vista del encuestado) y los 24 textos del resumen de inicio que faltaban. |
| `frontend/src/routes/(authentication)/login/+page.svelte` | Pie del ingreso (at.4): «AT-GRCA usa CISO Assistant Community, de intuitem, con licencia AGPL-3.0» y enlace al código fuente de este repositorio. |
| `frontend/src/lib/components/SideBar/SideBarFooter.svelte` | «Acerca de AT-GRCA» muestra producto, base (CISO Assistant Community, AGPL-3.0) y enlace al código fuente (at.4). |
| `frontend/src/routes/(authentication)/first-connexion/+page.svelte` | Sin los puntos que se agregaban al saludo (at.4). |
| `frontend/src/routes/(app)/+layout.svelte`, `(authentication)/login/+page.svelte`, `quantitative-risk-studies/[id=uuid]/executive-summary/+page.svelte` | El título de la pestaña dice «AT-GRCA» (at.3). |
| `frontend/src/lib/components/ChatWidget/ChatWidget.svelte` | El asistente de IA se presenta como «AT-GRCA» (at.3). |
| `frontend/src/routes/(authentication)/login/FormCard.svelte` | El botón de ingreso con SSO es azul lleno, el más visible (at.3). |
| `frontend/src/routes/(app)/(internal)/analytics/SummaryBriefing.svelte` | El resumen de inicio usa el color primario en vez de morados fijos (at.3). |
| `.github/workflows/at-grca-frontend.yml` (nuevo) | Arma la imagen `ghcr.io/athanortech/at-grca-ca-frontend` para amd64 y arm64. |
| `.github/workflows/at-grca-vista-previa.yml` (nuevo) | Levanta CISO Assistant con esa imagen dentro de GitHub y saca capturas para revisar cómo se ve. |
| `ATHANOR.md` (este archivo) | Explicación de los cambios. |

Las demás acciones de GitHub (`.github/workflows/`) vienen de intuitem y están **desactivadas** en este repositorio.

## Actualización mensual

1. `git fetch intuitem --tags` y `git merge vX.Y.Z` (la versión nueva de intuitem) en `main`.
2. Resolver los choques si los hay: solo pueden estar en los archivos de la tabla.
3. Desactivar las acciones nuevas que haya traído intuitem (`gh workflow list`, `gh workflow disable`).
4. Etiquetar `vX.Y.Z-at.1` y subir la etiqueta: GitHub arma la imagen.
5. En la instalación de AT-GRCA, cambiar la versión del frontend y la del backend a la misma `vX.Y.Z`.
