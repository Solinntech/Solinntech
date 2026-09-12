# GUÍA PASO A PASO PARA PUBLICAR EN GITHUB PAGES

## ✅ ANTES DE EMPEZAR - Requisitos

### 1. Verificar que Git está instalado

Abre **PowerShell** (no Command Prompt) y copia esto:

```powershell
git --version
```

**Resultado esperado:** Algo como `git version 2.40.0.windows.1`

❌ Si dice "no se reconoce el comando":
- Descarga e instala Git: https://git-scm.com/download/win
- Reinicia PowerShell
- Intenta de nuevo

### 2. Verificar tu cuenta GitHub

- ¿Ya tienes cuenta? Sí ❌ No
- Si no tienes: Crea una en https://github.com/signup

---

## 📝 PASO 1: CREAR REPOSITORIO EN GITHUB

1. **Abre GitHub** → https://github.com
2. **Inicia sesión** con tu cuenta
3. En la esquina superior derecha, haz clic en **+** → **New repository**
4. Completa así:
   - **Repository name:** `solinntech-website`
   - **Description:** (opcional) "Sitio web oficial de SolinnTech"
   - **Visibility:** Public
   - **NO marques:** "Add a README file" (ya tenemos uno)
5. Haz clic en **Create repository**

**Copiar la URL de clonación:**
- Verás un botón verde **Code** → Haz clic
- Copia el enlace HTTPS (algo como: `https://github.com/TU_USUARIO/solinntech-website.git`)
- Guarda ese enlace en Notepad

---

## 🚀 PASO 2: SUBIR ARCHIVOS DESDE TU COMPUTADORA

1. **Abre PowerShell**
   - Presiona `Windows + R`
   - Escribe `powershell`
   - Presiona Enter

2. **Navega a la carpeta del proyecto:**

```powershell
cd "C:\Users\Andres M\Documents\solinntech-website"
```

Presiona Enter.

3. **Inicia Git:**

```powershell
git init
```

4. **Agrega todos los archivos:**

```powershell
git add .
```

5. **Crea un commit:**

```powershell
git commit -m "Initial commit: SolinnTech website"
```

6. **Renombra la rama a 'main':**

```powershell
git branch -M main
```

7. **Agrega el repositorio remoto** (reemplaza `TU_USUARIO`):

```powershell
git remote add origin https://github.com/TU_USUARIO/solinntech-website.git
```

8. **Sube los archivos:**

```powershell
git push -u origin main
```

**Te pedirá autenticación:**
- Opción recomendada: **Crear un Personal Access Token**
  1. En GitHub, ve a **Settings** → **Developer settings** → **Personal access tokens**
  2. Crea un token nuevo con permisos `repo`
  3. Cópialo (aparece una sola vez)
  4. En PowerShell, cuando pida "password", pega el token

---

## 🔧 PASO 3: ACTIVAR GITHUB PAGES

1. **Abre GitHub** → Tu repositorio `solinntech-website`
2. Haz clic en **Settings** (engranaje arriba a la derecha)
3. En el menú izquierdo, busca **Pages** (más abajo en la lista)
4. En "Source", selecciona:
   - Branch: `main`
   - Folder: `/ (root)`
5. Haz clic en **Save**

**Espera 1-2 minutos.** Verás un mensaje:
> "Your site is published at https://tuusuario.github.io/solinntech-website"

✅ **Tu sitio está online.** Puedes visitarlo en ese enlace.

---

## 🌐 PASO 4: USAR TU DOMINIO PERSONALIZADO

### Opción A: Ya tienes el dominio registrado

1. **En GitHub:**
   - Ve a **Settings** → **Pages**
   - En "Custom domain", escribe: `solinntech.com`
   - Presiona **Save**
   - GitHub mostrará instrucciones de DNS

2. **En tu registrador de dominio** (Namecheap, GoDaddy, Hostinger, etc):
   - Inicia sesión
   - Busca "DNS Records" o "Manage DNS"
   - Elimina los A records antiguos (si existen)
   - Agrega estos **4 A records**:

```
Host: @        Type: A       Value: 185.199.108.153
Host: @        Type: A       Value: 185.199.109.153
Host: @        Type: A       Value: 185.199.110.153
Host: @        Type: A       Value: 185.199.111.153
```

   - Si tienes un registro CNAME para `www`, asegúrate que apunte a: `tuusuario.github.io`

   - **Espera 24-48 horas** (a veces funciona en minutos)

### Opción B: Necesitas registrar el dominio

Opciones recomendadas:
- **Namecheap** (confiable, barato)
- **GoDaddy** (bien conocido)
- **Google Domains** (fácil de usar)

Después de registrarlo, sigue la **Opción A**.

---

## ✅ VERIFICAR QUE FUNCIONA

1. Espera 10-15 minutos después de los cambios de DNS
2. Abre tu navegador
3. Escribe: `https://solinntech.com`
4. Deberías ver tu sitio SolinnTech

---

## 🔄 HACER CAMBIOS EN EL FUTURO

Cada vez que actualices `index.html`:

```powershell
cd "C:\Users\Andres M\Documents\solinntech-website"

# Edita el archivo en VSCode

# Luego:
git add .
git commit -m "Descripción de lo que cambió"
git push
```

El sitio se actualiza automáticamente en 1-2 minutos.

---

## ❓ PROBLEMAS COMUNES

**P: "fatal: not a git repository"**
R: Asegúrate de estar en la carpeta correcta. Ejecuta: `pwd` y verifica que muestre la carpeta del proyecto.

**P: "error: Repository not found"**
R: Revisa que la URL sea correcta (reemplazaste `TU_USUARIO`). Cópiala de nuevo desde GitHub.

**P: Mi dominio no apunta al sitio**
R: Los cambios de DNS demoran. Espera 24 horas. Verifica que los A records sean exactos.

**P: Me pide usuario y contraseña**
R: GitHub no acepta contraseña directa. Usa un Personal Access Token (ver Paso 2, punto 7).

---

**¿Necesitas ayuda?** Pregunta en: https://github.com/support
