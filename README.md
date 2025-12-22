# 🧭 BitSealer — Plataforma de sellado de tiempo sobre Bitcoin

**BitSealer** es una aplicación Full-Stack que permite **sellar archivos digitalmente** registrando su huella criptográfica (hash SHA-256) en la **blockchain de Bitcoin**, garantizando su existencia y autenticidad en el tiempo.

---

## 🚀 Funcionalidades actuales

✅ Registro y autenticación de usuarios (JWT + BCrypt)  
✅ Subida segura de archivos con control de tamaño  
✅ Cálculo y almacenamiento de hash SHA-256  
✅ Sellado temporal de archivos usando OpenTimestamps  
✅ Anclaje de pruebas en la blockchain de Bitcoin  
✅ Gestión de estados del sellado (PENDING / ANCHORING / SEALED)  
✅ Comunicación asíncrona con microservicio de timestamping  
✅ Reintentos automáticos con backoff exponencial para comprobar estado del .ots 
✅ Persistencia del TXID cuando existe transacción Bitcoin  
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
- Dashboard con métricas y gráficos  
- Interfaz moderna con TailwindCSS  

### ⛓️ [Microservicio Stamper— OpenTimestamps](https://github.com/BitSealer/bitsealer-stamper)
- Microservicio especializado en sellado temporal (worker)
- Implementado en Python con FastAPI
- Generación inicial de proofs OpenTimestamps (.ots)
- Upgrade de proofs bajo demanda hasta anclaje en Bitcoin
- Detección técnica del estado del proof (PENDING / ANCHORING / SEALED)
- Extracción del TXID cuando existe transacción Bitcoin
- Comunicación **stateless** con el backend principal vía REST
- El backend principal gestiona estados, persistencia y lógica de negocio

---
