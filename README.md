# 🧭 BitSealer — Plataforma de sellado de tiempo sobre Bitcoin

**BitSealer** es una aplicación Full-Stack que permite **sellar archivos digitalmente** registrando su huella criptográfica (hash SHA-256) en la **blockchain de Bitcoin**, garantizando su existencia y autenticidad en el tiempo.

---

## 🚀 Funcionalidades actuales

✅ Registro y autenticación de usuarios (JWT + BCrypt)  
✅ Subida y cálculo de hash SHA-256 de archivos  
✅ Historial de archivos sellados por usuario  

---

## 🧩 Módulos

### ⚙️ [Backend API — Spring Boot](https://github.com/BitSealer/bitsealer-backend)
- Controladores REST con JSON puro
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
