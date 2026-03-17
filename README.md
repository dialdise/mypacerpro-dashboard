# 🏃 MyPacerPro — Dashboard Operativo

Dashboard web completo para gestión de alumnos, coaches, cumpleaños y finanzas.  
**Se conecta directamente a tu Google Sheet** — sin backend, sin base de datos.

---

## 🚀 Deploy en GitHub Pages (3 pasos)

### Paso 1 — Crear el repositorio
1. Ve a [github.com](https://github.com) → **New repository**
2. Nombre: `mypacerpro-dashboard` (o el que quieras)
3. Visibilidad: **Public** (requerido para GitHub Pages gratis)
4. Click en **Create repository**

### Paso 2 — Subir el archivo
**Opción A — Desde la web de GitHub:**
1. En tu repositorio vacío, click en **uploading an existing file**
2. Arrastra el archivo `index.html`
3. Click **Commit changes**

**Opción B — Desde terminal (si tienes Git):**
```bash
git init
git add index.html
git commit -m "Add MyPacerPro dashboard"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/mypacerpro-dashboard.git
git push -u origin main
```

### Paso 3 — Activar GitHub Pages
1. En tu repositorio → **Settings** → **Pages** (menú izquierdo)
2. Source: **Deploy from a branch**
3. Branch: **main** → carpeta **/ (root)**
4. Click **Save**
5. En ~2 minutos tu dashboard estará en:  
   **`https://TU_USUARIO.github.io/mypacerpro-dashboard`**

---

## 📊 Funcionalidades

| Sección | Contenido |
|---------|-----------|
| **Resumen** | KPIs clave, gráfico de crecimiento, disciplinas, carga por coach |
| **Historial** | Evolución mensual completa desde Oct 2024, tabla con % variación |
| **Coaches** | Cards individuales, historial por mes, participación, pico histórico |
| **Cumpleaños** | Hoy, próximos 7 días, resto del mes — actualizado automáticamente |
| **Finanzas** | Ingresos por mes, pago coaches, gastos CAJA, últimos registros |

---

## 🔄 Cómo funciona la conexión

El dashboard usa la **API pública de Google Sheets** (gviz/tq) para leer los datos.  
Tu hoja debe estar configurada como **"Cualquiera con el enlace puede ver"**.

**Hojas que se leen:**
- `HISTORIAL MEMBRESIAS` → timeline de alumnos activos
- `CONTROL DE INGRESOS` → registro de pagos
- `BASE ALUMNOS` → alumnos activos + fechas de nacimiento
- `CAJA` → gastos operativos
- `DATA COACH` → coaches y tarifas

---

## ⚙️ Configuración

Si cambias el Google Sheet, edita esta línea en `index.html`:

```javascript
const SHEET_ID = '1FLMEqXf3enIMDr8fziXFvnEKwnlhhiUd6JYjmQentOQ';
```

Reemplaza con el ID de tu nueva hoja (está en la URL de Google Sheets).

---

## 📱 Compatibilidad

- ✅ Chrome, Firefox, Safari, Edge
- ✅ Desktop y tablet
- ✅ Sin instalación — solo un archivo HTML
- ✅ Sin backend ni servidor

---

## 🔐 Permisos de Google Sheet

Para que el dashboard funcione, tu hoja necesita ser **pública de solo lectura**:

1. En Google Sheets → click en **Compartir** (arriba derecha)
2. En "Acceso general" → cambiar a **"Cualquier persona con el enlace"**
3. Permisos: **Lector** (no escritor)
4. Click **Copiar enlace** y **Listo**

> ⚠️ Esto permite que cualquier persona con el enlace **lea** (no edite) tu hoja.  
> Tus datos financieros y de alumnos serán visibles para quien tenga el link del dashboard.  
> Si prefieres privacidad total, considera autenticación con Google OAuth (requiere backend).

---

*Generado para MyPacerPro © 2026*
