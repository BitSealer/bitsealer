# 🧭 BitSealer — Plataforma de sellado de tiempo sobre Bitcoin

**BitSealer** es una aplicación Full-Stack que permite **sellar archivos digitalmente** registrando su huella criptográfica (hash SHA-256) en la **blockchain de Bitcoin**, garantizando su existencia y autenticidad en el tiempo.

> Proyecto modular desarrollado en **Spring Boot 3 + React**, con un enfoque en seguridad, escalabilidad y trazabilidad.

---

## 🧱 Arquitectura del ecosistema

BitSealer/
├── bitsealer-backend/ → API REST (Spring Boot 3, PostgreSQL, JWT)
├── bitsealer-frontend/ → Panel web (React + Tailwind + Axios)
└── bitsealer-timestamp/ → Microservicio Blockchain (en desarrollo)

Cada módulo puede ejecutarse de forma independiente o en conjunto mediante Docker.

---

## ⚙️ Tecnologías principales

| Capa | Tecnologías |
|------|--------------|
| **Backend** | Java 17 · Spring Boot 3.5 · Spring Security 6 · JJWT 0.12.5 · PostgreSQL 14 · Flyway · Testcontainers |
| **Frontend** | React · Vite · TailwindCSS · Axios · Context API |
| **Infraestructura** | Docker · Docker Compose · JWT Auth · REST API |
| **Blockchain (próximamente)** | OpenTimestamps · Bitcoin Core RPC / API Wrapper |

---

## 🚀 Funcionalidades actuales

✅ Registro y autenticación de usuarios (JWT + BCrypt)  
✅ Subida y cálculo de hash SHA-256 de archivos  
✅ Historial de archivos sellados por usuario  
✅ Dashboard con métricas básicas y sellos recientes  
🔒 Seguridad implementada con Spring Security + filtros JWT  
⚙️ Preparado para despliegue con Docker (PostgreSQL + API + Frontend)

---

## 🧩 Próximas implementaciones

🔗 Sellado real en blockchain mediante **OpenTimestamps**  
📊 Gráficas de uso y estadísticas avanzadas en el Dashboard  
💬 Sistema de notificaciones por correo y API REST pública  
💰 Integración con sistema de tarifas BTC / fee market  

---

## 🧠 Filosofía del proyecto

BitSealer nace con el objetivo de **acercar la tecnología blockchain a la verificación documental**.  
El sistema no guarda archivos, solo sus huellas criptográficas, asegurando privacidad y trazabilidad.

La arquitectura se ha diseñado siguiendo principios **Clean Architecture** y separación por capas:  
`Controller → Service → Repository → Model`, con DTOs intermedios y pruebas integradas mediante **Testcontainers**.

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

## 🧰 Ejecución local

### 1. Backend (Spring Boot)
```bash
cd bitsealer-backend
./mvnw spring-boot:run
