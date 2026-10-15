# Mantenimiento de calderas

App web instalable (PWA) para llevar clientes, trabajos de mantenimiento, pagos pendientes y recordatorios anuales por WhatsApp. Funciona sin internet y sin cuentas: los datos quedan en el dispositivo.

## Funciones

- Clientes: nombre, teléfono (WhatsApp) y dirección obligatorios; nota opcional.
- Trabajos (mantenimiento, instalación o reparación): equipo, qué se hizo, qué se cambió, observaciones y recomendaciones.
- Pago por trabajo: pendiente o pagado. Los pendientes se ven en el inicio.
- Recordatorio: avisa 330 días después del último trabajo (configurable). El botón abre WhatsApp con el mensaje armado.
- Ajustes: nombre de la empresa, logo, color y texto del mensaje.
- Respaldo: descarga y restauración de un archivo `.json` en el dispositivo.

## Uso

No requiere compilar ni instalar nada.

```bash
python3 -m http.server 8000
# abrir http://localhost:8000
```

Para instalarla en el celular tiene que estar publicada en una dirección https (cualquier hosting estático sirve; la raíz del repositorio es el directorio a publicar).

## Datos

Se guardan en el almacenamiento del navegador del dispositivo. Si se borran los datos del navegador o se cambia de equipo se pierden, por eso conviene usar el respaldo desde Ajustes. Los archivos `respaldo-*.json` contienen datos de clientes y están excluidos en `.gitignore`.

## Archivos

- `index.html`: la app (HTML, estilos y lógica).
- `manifest.webmanifest`: datos de instalación.
- `sw.js`: service worker para el funcionamiento sin conexión.
- `icons/`: iconos de instalación.
