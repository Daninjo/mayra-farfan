# Lic. Mayra Farfán · Nutrición y composición corporal (InBody)

Landing + flyer para el consultorio de May en Las Cañitas.

- **Landing**: https://daninjo.github.io/mayra-farfan/ (GitHub Pages desde `main`)
- **Flyer para WhatsApp / Instagram**: `flyer/flyer-wa.png` (1080×1350, 4:5)
- **Flyer para imprimir**: `flyer/flyer-a5.pdf` (A5, sin sangrado; pedir a la imprenta "ajustar a página")
- **QR**: `flyer/qr.svg` / `flyer/qr.png` → apunta a la landing con `?src=flyer_qr`

## Cómo funciona el origen de cada consulta

Todos los botones de la landing abren WhatsApp con un mensaje precargado. La landing no publica precios: los honorarios los responde May (y después el agente) en el chat. El mensaje cambia según cómo llegó la persona:

| Link | Mensaje que llega |
|---|---|
| `…/mayra-farfan/?src=flyer_qr` (QR) | "Hola May! Escaneé el QR de tu flyer y quiero reservar un turno" |
| `…/mayra-farfan/?src=flyer_wa` (link compartido con el flyer) | "Hola May! Vi tu flyer y quiero reservar un turno" |
| `…/mayra-farfan/?src=ig` (bio de Instagram) | "Hola May! Vengo de tu Instagram y quiero reservar un turno" |
| `…/mayra-farfan/` | "Hola May! Vi tu página y quiero reservar un turno" |

Si tocan "Reservar turno" dentro de un servicio, se agrega una línea "Motivo: …" con el servicio (descenso de peso, salud digestiva, condiciones metabólicas, nutrición infantil).

## Texto sugerido para compartir el flyer por WhatsApp

> ¿Sabés de qué está hecho tu cuerpo? 💪
> Ahora tengo InBody en el consultorio: en 15 minutos sabés cuánto es músculo, cuánto es grasa y cuánto es agua, y te llevás un plan de acción personalizado.
> Toda la info acá 👉 https://daninjo.github.io/mayra-farfan/?src=flyer_wa

## Editar

- Textos y horarios: `index.html` (una sola página, sin build). Secciones: hero, enfoque, `#servicios`, `#consulta`, `#inbody`, `#sobre` (bio y trayectoria de LinkedIn), reseñas, `#turnos`.
- Flyer: `flyer/flyer.html`. Para regenerar el PNG/PDF se usa Chrome headless (ver `flyer/render.md`).
- Si se compra dominio propio (ej. `mayrafarfan.com`): agregar archivo `CNAME` con el dominio y configurar DNS. GitHub redirige la URL vieja `daninjo.github.io/mayra-farfan` al dominio nuevo, así que los QR ya impresos siguen funcionando.
