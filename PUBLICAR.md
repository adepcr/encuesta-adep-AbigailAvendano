# Publicar la encuesta (Vercel)

La encuesta se publica en **Vercel**, desde este repositorio de la organización de ADEP.
No necesita llaves, contraseñas ni Firebase.

- Encuesta: **https://encuesta-adep.vercel.app/**
- Resultados (solo organizadores, con clave): **https://encuesta-adep.vercel.app/resultados.html**

Cada cambio que se sube a `main` se publica solo en Vercel (tarda menos de un minuto).
El proyecto en Vercel se llama `encuesta-adep` (Framework Preset: *Other*, sin variables ni configuración).

Las respuestas no dependen de la página: siguen llegando a la hoja de Google de la cuenta de Gmail de ADEP
(vea [INSTALAR-BACKEND.md](INSTALAR-BACKEND.md)).

## Respaldo: GitHub Pages

También se puede publicar con GitHub Pages en https://adepcr.github.io/encuesta-adep/ (respaldo).

### Activar GitHub Pages (una sola vez)

1. Abra <https://github.com/adepcr/encuesta-adep-AbigailAvendano/settings/pages>.
2. **Source:** *Deploy from a branch*. **Branch:** `main` y carpeta `/ (root)`. Presione **Save**.
3. En uno o dos minutos la encuesta queda en la dirección de respaldo.

Desde entonces, cada cambio que se sube a `main` se publica solo (tarda uno o dos minutos).

## La dirección anterior (adep-encuesta.web.app): desactivada

Antes la encuesta se publicaba en Firebase Hosting (proyecto `adep-encuesta`, cuenta de Gmail de ADEP).

- El **4 de noviembre de 2026** se desactivó el sitio: `adep-encuesta.web.app` ya no abre la encuesta.
  La única dirección es la de GitHub Pages (arriba). Las respuestas guardadas en la hoja de Google no se tocaron.
- El proyecto de Firebase sigue existiendo en la cuenta de Gmail de ADEP, sin sitio publicado y sin costo (plan Spark).
  Para entrar a Firebase, Google exige verificación en dos pasos en esa cuenta desde el 6 de noviembre de 2026.
- Se desactivó desde una terminal con:
  ```
  npx firebase-tools login
  npx firebase-tools hosting:disable --project adep-encuesta
  ```
  (La consola web nueva no muestra un botón para desactivar.) Para volver a encenderlo habría que publicar
  de nuevo con `firebase deploy`, pero no hace falta: la encuesta vive en GitHub Pages.

### Antes de entregar

- [x] **Sitio viejo en Firebase (`adep-encuesta`): desactivado** el 4 de noviembre de 2026.
- [x] **Envío por Microsoft 365: no se activó** (revisado el 4 de noviembre de 2026). En Apps Script solo están
  `CLAVE_RESULTADOS`, `CORREOS` y `ULTIMO_RESUMEN`; no hay propiedades `MS_…`. Los correos salen por la cuenta
  de Gmail de ADEP y no hay ningún secreto de Microsoft que entregar. Si más adelante se activa, vea
  [ENVIAR-CON-MICROSOFT.md](ENVIAR-CON-MICROSOFT.md) y anote en la entrega quién administra Microsoft 365
  y cuándo vence el secreto (nunca el valor del secreto).
