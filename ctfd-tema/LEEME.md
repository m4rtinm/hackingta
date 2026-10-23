# Tema CTFd · Hackingta

Tres bloques que se pegan en **Admin → Config → Theme** de CTFd:

| Archivo | Campo de CTFd |
|---|---|
| `Theme_Header.html` | Theme Header |
| `Theme_Footer.html` | Theme Footer |
| `Index.html` | Index Page Content |

El orden importa: la cabecera define la paleta y las fuentes que usan los otros dos.

## Dónde se edita cada cosa

- **Contenido de la portada** (nombre, enlaces, logos, reglas, requisitos):
  bloque `window.HK_CTF` al comienzo de `Index.html`.
- **Título de la pestaña y mensajes de consola**:
  bloque `window.HK_PIE` al comienzo de `Theme_Footer.html`.
- **Colores, radios y tipografías**: bloque `:root` al comienzo de `Theme_Header.html`.
  Son los mismos tokens de la landing del evento.

## Logos

Súbelos en **Admin → Files**, copia la ruta que entrega CTFd (`/files/…`)
y pégala en `HK_CTF.logos`. Los que queden en `""` no se muestran.

## Cuidado al editar

Las variables de configuración van como `window.HK_CTF = {…}`, no como
`const HK_CTF = {…}`. Un `const` a nivel superior **no** queda accesible
desde el otro bloque de script y la portada se queda en blanco.
