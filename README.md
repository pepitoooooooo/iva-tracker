# Control de IVA

Página de una sola pieza (`index.html`) para llevar el registro del pago mensual del IVA de la empresa.

## Qué hace
- Muestra el estado del mes actual: próximo, dentro de plazo (15–20), atrasado, o pagado.
- Botón para subir una foto/captura del comprobante (se guarda en el navegador, en `localStorage`).
- Calendario navegable con el rango 15–20 marcado.
- Historial de los últimos 12 meses, con miniatura del comprobante cuando existe.

## Cómo subir esto a un repo nuevo en GitHub
1. Entra a github.com y crea un repositorio nuevo (por ejemplo `iva-tracker`), público.
2. Sube este `index.html` (y este `README.md`) arrastrándolos a la página del repo, o con "Add file → Upload files".
3. Ve a **Settings → Pages**, en "Branch" elige `main` y carpeta `/ (root)`, guarda.
4. En un par de minutos la página queda disponible en:
   `https://TU-USUARIO.github.io/iva-tracker/`

## Importante sobre el comprobante
Los comprobantes se guardan **en el navegador donde los subas** (localStorage). Para verlos también desde otro celular o computador, configura la sincronización con GitHub descrita más abajo — sin eso, cada dispositivo queda con su propio historial.

## Recordatorios de Google Calendar
Quedaron creados recordatorios recurrentes (mensuales) en tu Google Calendar principal:
- Días 15 al 19: una notificación a las 09:00.
- Día 20: cinco notificaciones (09:00, 12:30, 16:00, 19:30 y 22:30) para evitar la multa de medianoche.

## Sincronizar entre dispositivos
La página guarda los pagos en el navegador (localStorage), así que por defecto no se ven entre celular y PC. Para eso está la tarjeta "Sincronizar entre dispositivos":

1. En GitHub: **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. Dale acceso **solo a este repositorio**, con permiso **Contents: Read and write**.
3. En la página, pega tu usuario de GitHub, el nombre del repo, y ese token. Guarda.
4. Repite el mismo paso 3 (mismo usuario/repo/token) en cada dispositivo que quieras sincronizar.
5. Toca **🔄 Sincronizar ahora** después de subir un comprobante — sube los datos a un archivo `iva-data.json` en el repo. Al abrir la página en otro dispositivo ya configurado, se trae automáticamente lo último al cargar.

El token queda guardado solo en el navegador de cada dispositivo, nunca se sube a GitHub — solo se usa para autenticar las llamadas a la API.

## Botón "🔔 Avisar a Claude"
Como una página estática no puede enviarme un aviso de forma automática (no hay backend ni conexión directa entre la web y el chat), este botón:
1. Marca el mes como pagado en la página.
2. Copia al portapapeles un mensaje listo para pegar.
3. Abre Claude en una pestaña nueva.

Solo falta que pegues (Ctrl+V) y envíes el mensaje para que Claude cancele los recordatorios de Calendar que falten ese mes.
