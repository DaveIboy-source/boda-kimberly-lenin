# 💍 Boda Kimberly & Lenin — Sistema de Invitación Digital

## 📁 Archivos incluidos

| Archivo | Descripción |
|---|---|
| `index.html` | Invitación pública (la que ven los invitados) |
| `dashboard.html` | Panel para organizadores (tiempo real) |
| `README.md` | Este archivo de instrucciones |

---

## 🚀 PASO 1: Subir a GitHub Pages (gratis)

1. Ve a [github.com](https://github.com) y crea una cuenta si no tienes.
2. Haz clic en **"New repository"** (botón verde).
3. Nombre del repositorio: `boda-kimberly-lenin` (o el que prefieras).
4. Marca la opción **"Public"**.
5. Haz clic en **"Create repository"**.
6. Dentro del repositorio, haz clic en **"uploading an existing file"**.
7. Sube los 3 archivos: `index.html`, `dashboard.html`, `README.md`.
8. Haz clic en **"Commit changes"**.
9. Ve a **Settings → Pages** (menú izquierdo).
10. En "Source" selecciona **"Deploy from a branch"** → rama: **main** → carpeta: **/ (root)**.
11. Guarda. En 2-3 minutos tendrás tu URL:

```
https://TU-USUARIO.github.io/boda-kimberly-lenin/
```

**¡Esa es la URL que mandas a los invitados!**

Para el dashboard:
```
https://TU-USUARIO.github.io/boda-kimberly-lenin/dashboard.html
```

---

## 📊 PASO 2: Conectar Google Sheets (para recibir confirmaciones)

### 2a. Crear el Google Form

1. Ve a [forms.google.com](https://forms.google.com) e inicia sesión.
2. Crea un formulario nuevo con estas preguntas (en orden):
   - Nombre completo (Respuesta corta)
   - WhatsApp / Teléfono (Respuesta corta)
   - ¿Asistirás? (Opción múltiple: "Sí asiste" / "No puede asistir")
   - Número de acompañantes (Opción múltiple: 0, 1, 2, 3, 4)
   - Preferencia de menú (Opción múltiple: Carne, Pollo, Pescado, Vegetariano)
   - Alergias o restricciones alimentarias (Respuesta corta)
   - Canción favorita (Respuesta corta)
   - Mensaje para los novios (Párrafo)

3. Haz clic en los **3 puntos (⋮)** arriba a la derecha → **"Obtener código de inserción"**.
4. En el mismo menú → **"Ir a la hoja de cálculo"** (esto crea el Google Sheet vinculado).

### 2b. Obtener los IDs del formulario

1. Abre el formulario en modo edición.
2. Haz clic derecho → **"Ver código fuente de la página"**.
3. Busca (Ctrl+F) `entry.` — encontrarás los IDs de cada campo.
4. Abre `index.html` y reemplaza en la sección de configuración:

```javascript
const SHEETS_URL = "https://docs.google.com/forms/d/e/TU_FORM_ID/formResponse";
const FIELD_NOMBRE    = "entry.XXXXXXXXX";  // ID del campo Nombre
const FIELD_TELEFONO  = "entry.XXXXXXXXX";  // ID del campo Teléfono
const FIELD_ASISTENCIA= "entry.XXXXXXXXX";  // ID del campo Asistencia
const FIELD_ACOMP     = "entry.XXXXXXXXX";  // ID del campo Acompañantes
const FIELD_MENU      = "entry.XXXXXXXXX";  // ID del campo Menú
const FIELD_ALERGIA   = "entry.XXXXXXXXX";  // ID del campo Alergias
const FIELD_CANCION   = "entry.XXXXXXXXX";  // ID del campo Canción
const FIELD_MENSAJE   = "entry.XXXXXXXXX";  // ID del campo Mensaje
```

### 2c. Publicar el Sheet para el Dashboard

1. Abre el Google Sheet vinculado al formulario.
2. Archivo → **Compartir** → **Publicar en la web**.
3. Selecciona la hoja (Sheet1) → formato: **Valores separados por comas (.csv)**.
4. Haz clic en **Publicar** → copia el URL generado.
5. Pega ese URL en el campo de configuración del dashboard.

---

## 🎵 PASO 3: Agregar la música (Photograph - Ed Sheeran)

> ⚠️ Por derechos de autor, no puedes hospedar el archivo MP3 directamente en GitHub.
> Usa una de estas opciones legales:

### Opción A — YouTube (recomendada)
Reemplaza en `index.html` la línea del `<audio>` con:

```html
<iframe id="ytAudio" 
  src="https://www.youtube.com/embed/nSDgHBa17BIDA?autoplay=0&loop=1&playlist=nSDgHBa17BIDA&enablejsapi=1" 
  style="display:none" 
  allow="autoplay">
</iframe>
```
*(reemplaza `nSDgHBa17BIDA` con el ID real del video de YouTube)*

### Opción B — Archivo propio
Si tienes el archivo `photograph.mp3` legalmente, agrégalo al repositorio y cambia:
```html
<source src="photograph.mp3" type="audio/mpeg">
```

---

## 📸 PASO 4: Agregar la foto de los novios

En `index.html`, busca esta línea:
```html
<img class="hero-photo" src="https://images.unsplash.com/..." alt="Kimberly y Lenin">
```
Reemplaza el `src` por:
- La URL de una foto subida a Google Drive (compartida como "Cualquiera con el enlace puede ver") → clic derecho en Drive → "Obtener enlace" → cambia `/view` por `/uc?export=view`
- O sube la foto al repositorio de GitHub y usa `src="tu-foto.jpg"`

---

## 🔗 URLs finales que compartir

| Quién | URL |
|---|---|
| Invitados | `https://TU-USUARIO.github.io/boda-kimberly-lenin/` |
| Organizadores | `https://TU-USUARIO.github.io/boda-kimberly-lenin/dashboard.html` |
| Google Sheet | Compartir solo con los organizadores |

---

## 💌 Texto para enviar por WhatsApp

```
✨ Kimberly & Lenin se casan ✨

El 4 de julio de 2026 en el Club Mariscal, Guatemala.

Estás cordialmente invitado/a a celebrar este día especial con nosotros.

👉 Abre tu invitación digital aquí:
https://TU-USUARIO.github.io/boda-kimberly-lenin/

Por favor confirma tu asistencia desde la invitación antes del 3 de julio. ¡Te esperamos! 💙
```

---

Con amor, Kimberly & Lenin — 4 · 07 · 2026
