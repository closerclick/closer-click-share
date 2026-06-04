# @closerclick/closer-click-share

UI compartida del ecosistema **CloserClick** para **compartir un enlace**. Web
Component `<closer-click-share>` (custom element, Shadow DOM) reutilizable por
cualquier app (Vue o vanilla): el **mismo** modal de compartir para pronosticador,
ajedrez, cuarenta, etc.

Muestra **QR** (autohosteado, generado en el cliente — sin servicios de terceros),
el **enlace** con botón de copiar, y botones de **redes** (WhatsApp, Telegram, X,
Facebook) + "Más" (Web Share API nativa).

Autohosteado, Shadow DOM, **sin JS de terceros ni cookies**, bilingüe es/en. No
toca identidad/transporte/almacenamiento: solo recibe una URL ya armada (los datos
de usuario viajan por `#fragment`, que no llega al servidor ni es indexable).

## Uso

```js
import '@closerclick/closer-click-share'
```

```html
<closer-click-share lang="es"></closer-click-share>
```

```js
const el = document.querySelector('closer-click-share')
el.url = 'https://cuarenta.closer.click/#table=ABC'
el.text = '¡Únete a mi mesa!'
el.open = true
el.addEventListener('cc-share-close', () => { el.open = false })
```

### Atributos / propiedades
- `url` — el enlace a compartir / del QR.
- `text` — texto corto para las redes.
- `lang` — `es` | `en`.
- `heading`, `hint` — textos opcionales.
- `open` — booleano: muestra/oculta el modal.

### Evento
- `cc-share-close` — al cerrar el modal.

### Tema (variables CSS)
`--ccs-bg`, `--ccs-text`, `--ccs-muted`, `--ccs-border`, `--ccs-accent`,
`--ccs-accent-text`, `--ccs-input-bg`, `--ccs-overlay`, `--ccs-radius`, `--ccs-shadow`.
