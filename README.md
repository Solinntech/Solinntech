# SolinnTech Website

Sitio web oficial de SolinnTech - Transformación Operacional para empresas que quieren crecer.

## Estructura

- `index.html` - Sitio completo en un archivo HTML estático
- `README.md` - Este archivo
- `.gitignore` - Archivos a ignorar en Git

## Publicar en GitHub Pages

### 1. Crear repositorio en GitHub

1. Ve a [github.com](https://github.com) y crea un nuevo repositorio llamado `solinntech-website`
2. NO inicialices con README (vamos a usar el que tenemos)
3. Copia el HTTPS URL del repositorio

### 2. Subir archivos desde tu computadora

Abre PowerShell en la carpeta del proyecto y ejecuta:

```powershell
# Navegar a la carpeta del proyecto
cd C:\Users\Andres M\Documents\solinntech-website

# Inicializar Git
git init

# Agregar todos los archivos
git add .

# Hacer commit inicial
git commit -m "Initial commit: SolinnTech website"

# Renombrar rama a main (GitHub Pages usa main por defecto)
git branch -M main

# Agregar repositorio remoto (reemplaza TU_USUARIO)
git remote add origin https://github.com/TU_USUARIO/solinntech-website.git

# Subir archivos
git push -u origin main
```

### 3. Activar GitHub Pages

1. Ve a tu repositorio en GitHub
2. **Settings** → **Pages**
3. En "Source", selecciona `main` branch
4. En "folder", deja `/root` (predeterminado)
5. Presiona "Save"

**El sitio se publicará en:** `https://TU_USUARIO.github.io/solinntech-website`

### 4. Configurar dominio personalizado (solinntech.com)

#### Si ya tienes el dominio registrado:

1. En GitHub, ve a **Settings** → **Pages**
2. En "Custom domain", escribe: `solinntech.com`
3. Presiona "Save"
4. GitHub creará automáticamente un archivo `CNAME`

#### En tu registrador de dominio (Namecheap, GoDaddy, etc):

1. Busca la sección de "DNS Records" o "Name Servers"
2. Agrega estos **A records** (apunta hacia GitHub):
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
3. O si tu registrador lo permite, agrega este **CNAME record**:
   ```
   www → TU_USUARIO.github.io
   ```

**Tiempo de propagación:** 24-48 horas (a veces minutos)

## Ediciones futuras

Para hacer cambios en el futuro:

```powershell
cd C:\Users\Andres M\Documents\solinntech-website

# Edita el index.html

# Luego:
git add .
git commit -m "Descripción de cambios"
git push
```

El sitio se actualizará automáticamente en GitHub Pages.

## Checklist antes de publicar

- [ ] Tienes cuenta GitHub
- [ ] Tienes el dominio solinntech.com (o lo tienes registrado)
- [ ] PowerShell instalado (Windows lo trae por defecto)
- [ ] Git instalado ([descargar](https://git-scm.com/download/win))

## Soporte

Para dudas sobre GitHub Pages: [docs.github.com/pages](https://docs.github.com/en/pages)
