# 🧭 BitSealer — Plataforma de sellado de tiempo sobre Bitcoin

**BitSealer** es una aplicación Full-Stack que permite **sellar archivos digitalmente** registrando su huella criptográfica (hash SHA-256) en la **blockchain de Bitcoin**, garantizando su existencia y autenticidad en el tiempo.

---

## 🧩 Módulos

### ⚙️ [Backend API — Spring Boot](https://github.com/BitSealer/bitsealer-backend)
- Controladores REST con JSON puro (sin Thymeleaf)  
- Seguridad con Spring Security 6 y JWT  
- Flyway para migraciones de base de datos  
- Tests unitarios y de integración con Testcontainers  

### 🖥️ [Frontend — React](https://github.com/BitSealer/bitsealer-frontend)
- Login / Registro de usuarios  
- Subida de archivos y visualización del historial  
- Dashboard con métricas y gráficos (en desarrollo)  
- Interfaz moderna con TailwindCSS  

### ⛓️ [Microservicio Timestamp — Blockchain (próximamente)](https://github.com/BitSealer/bitsealer-timestamp)
- Conexión con Bitcoin Core o nodos públicos  
- Generación y verificación de pruebas OpenTimestamps  
- Preparado para integración asincrónica con el backend principal  

---

## 🔄 Flujo general del ecosistema BitSealer

```mermaid
graph TD
    A[Usuario Web] -->|HTTP / JSON| B[BitSealer Frontend (React + Tailwind)]
    B -->|REST API / JWT| C[BitSealer Backend (Spring Boot + PostgreSQL)]
    C -->|Async Task / HTTP| D[BitSealer Timestamp (Microservicio Blockchain)]
    D -->|RPC / API| E[Bitcoin Network]
    C -->|Persistencia| F[(Base de Datos PostgreSQL)]

    click B "https://github.com/BitSealer/bitsealer-frontend" "Ver Frontend"
    click C "https://github.com/BitSealer/bitsealer-backend" "Ver Backend"
    click D "https://github.com/BitSealer/bitsealer-timestamp" "Ver Timestamp"

---

### 🧠 Explicación rápida

> 1️⃣ El usuario accede al **panel React** (frontend).  
> 2️⃣ Éste llama al **API REST Spring Boot** con autenticación JWT.  
> 3️⃣ El backend calcula y guarda el hash en PostgreSQL.  
> 4️⃣ Si se requiere sellado real, llama al microservicio **Timestamp**.  
> 5️⃣ El microservicio envía la transacción a la red **Bitcoin**.

---

💡 Consejo:  
Para darle un toque más pro, puedes poner el título encima con un emoji, así:

```markdown
## 🧭 Arquitectura general del ecosistema

---

### 🖼️ (B) Versión visual (si prefieres imagen)
Puedes generar una imagen automática de ese diagrama con Mermaid Live Editor:
👉 [https://mermaid.live/](https://mermaid.live/)  

Copia el bloque anterior allí, exporta como `.png` y súbelo a tu repo en `/docs/diagram.png`,  
luego pon esto en el README:

```markdown
## 🔄 Flujo general del ecosistema BitSealer
![Arquitectura BitSealer](./docs/diagram.png)

---

## 🚀 Funcionalidades actuales

✅ Registro y autenticación de usuarios (JWT + BCrypt)  
✅ Subida y cálculo de hash SHA-256 de archivos  
✅ Historial de archivos sellados por usuario  
✅ Dashboard con métricas básicas y sellos recientes  
🔒 Seguridad implementada con Spring Security + filtros JWT  
⚙️ Preparado para despliegue con Docker (PostgreSQL + API + Frontend)

---

## 🧰 Ejecución local

### 1. Backend (Spring Boot)
```bash
cd bitsealer-backend
./mvnw spring-boot:run
