# 🚀 Guía de instalación — Profile README

## El truco del repo especial

GitHub renderiza automáticamente el README de un repo que **tenga el mismo nombre que tu usuario**. En tu caso:

```
github.com/hectorcanaimero/hectorcanaimero
```

Ese repo es el que aparece como tu "profile". Si no lo tienes, lo creamos en 2 minutos.

---

## Opción A — Via GitHub Web (más rápido, recomendado)

### 1. Crear el repo especial

1. Anda a https://github.com/new
2. **Repository name:** `hectorcanaimero` (idéntico a tu usuario)
3. ⚠️ GitHub te mostrará un mensaje verde: **"You found a secret! ... This is a special repository."** — eso confirma que está bien.
4. Marca: ✅ **Public**
5. Marca: ✅ **Add a README file**
6. Click **Create repository**

### 2. Subir los archivos

Una vez creado el repo:

1. Click en **Add file** → **Upload files**
2. Arrastra:
   - `README.md`
   - La carpeta `assets/` completa (con `banner.svg` adentro)
3. Commit message: `feat: add custom profile README`
4. Click **Commit changes**

### 3. Verificar

Anda a https://github.com/hectorcanaimero — deberías ver el README renderizado en tu profile. ✨

---

## Opción B — Via Terminal (si prefieres CLI)

```bash
# 1. Crear el repo localmente
mkdir hectorcanaimero && cd hectorcanaimero
git init
git branch -M main

# 2. Copiar README.md y assets/banner.svg a esta carpeta

# 3. Commit inicial
git add .
git commit -m "feat: add custom profile README"

# 4. Crear el repo remoto (necesitas gh CLI)
gh repo create hectorcanaimero --public --source=. --push

# Si no tienes gh, créalo manualmente en github.com/new
# y luego:
git remote add origin https://github.com/hectorcanaimero/hectorcanaimero.git
git push -u origin main
```

---

## ⚠️ Cosas que debes ajustar antes de hacer push

Abre `README.md` y revisa estos puntos:

### 1. URLs de proyectos
Los enlaces a UseBot, VideoFlow y otros están como `#` placeholder. Cámbialos por las URLs reales si las tienes públicas:

```markdown
<h3>🤖 <a href="#">UseBot</a></h3>
            ^^^ ← cambiar por la URL real
```

### 2. Link a Condor-martech
Si la organización es **privada**, el badge se romperá visualmente. Opciones:
- **a)** Dejarla como está (el link dará 404 a quien no sea miembro, pero no rompe el README)
- **b)** Quitar el `<a href="...">` y dejar solo el texto
- **c)** Hacerla pública si quieres mostrar los repos

### 3. Portfolio
Tu bio actual apunta a `http://canaimeando.github.com` — verifica si ese sitio está vivo y actualizado, o cámbialo por uno nuevo.

### 4. Email / contacto
El README no incluye email por privacy. Si quieres añadirlo, agrega esto en la sección **Connect**:

```markdown
<a href="mailto:tu@email.com">
  <img src="https://img.shields.io/badge/Email-0F172A?style=for-the-badge&logo=gmail&logoColor=22D3EE" />
</a>
```

---

## 🎨 Servicios externos que usa el README

Estos se cargan automáticamente — **no necesitas configurar nada**, pero es bueno saber qué son:

| Servicio | Para qué sirve | URL |
|---|---|---|
| **readme-typing-svg** | Headline animado tipo máquina de escribir | demolab.com |
| **shields.io** | Badges (followers, repos, achievements, tech stack) | shields.io |
| **github-readme-stats** | Stats de commits y top languages | vercel.app |
| **github-readme-streak-stats** | Racha de commits | herokuapp.com |
| **github-readme-activity-graph** | Gráfico de actividad | vercel.app |
| **github-profile-trophy** | Trofeos por achievements | vercel.app |
| **komarev** | Contador de visitas al perfil | komarev.com |

Si alguno te falla en el futuro (a veces estos servicios tienen downtime), simplemente coméntalo en el README hasta que vuelva.

---

## 🔧 Customizaciones opcionales

### Cambiar la paleta de colores

El esquema actual es **slate dark + cyan + violet** (`#0F172A` / `#22D3EE` / `#A78BFA`). Para cambiarla, busca y reemplaza en el README:

- `0F172A` → tu color de fondo
- `22D3EE` → tu accent principal
- `A78BFA` → tu accent secundario

Esto afecta también todos los stat cards y el banner SVG.

### Esconder el contador de visitas

Borra esta línea:
```markdown
<img src="https://komarev.com/ghpvc/?username=hectorcanaimero..." />
```

### Cambiar el typing headline

En el bloque `readme-typing-svg`, edita el parámetro `lines=` separando frases con `;`. Cuidado con los espacios (usa `+`) y los caracteres especiales (URL-encode).

---

## 🧪 Tip pro: Pin tus mejores repos

GitHub te deja "fijar" hasta 6 repos en tu profile. Anda a tu profile → **Customize your pins** y elige:

1. **bot-whatsapp** (tu repo más popular, 11 stars)
2. **Magento-RdStation** (4 stars)
3. **shortener** (NestJS, demuestra backend)
4. **wooionic** (Ionic + WooCommerce, demuestra fullstack)
5. + 2 que tú elijas (idealmente algo de PideAI/UseBot si tienes algo público)

Esto se renderiza **abajo del README** y refuerza el "qué hago".

---

## ✅ Checklist final

- [ ] Repo `hectorcanaimero/hectorcanaimero` creado como **public**
- [ ] `README.md` y `assets/banner.svg` subidos
- [ ] URLs de proyectos actualizadas (no quedó ningún `#`)
- [ ] Pinned repos elegidos
- [ ] Bio principal de GitHub actualizada (opcional, pero recomendado): cambiar "Ao Infinito e alem..." por algo como `Building AI tools for LATAM retail · @PideAI · @UseBot`
- [ ] Verificado que el banner se renderiza en mobile y desktop

---

## 🆘 Si algo no se ve

- **Banner no aparece:** Verifica que `assets/banner.svg` esté en el path correcto. El README usa `./assets/banner.svg` (relativo al root del repo).
- **Stats cards en blanco:** Los servicios de Vercel a veces tardan 30-60s la primera vez. Refresca.
- **Typing animation no se mueve:** Algunos navegadores cachean SVGs. Hard refresh (Cmd+Shift+R / Ctrl+Shift+F5).

Listo. 🚀
