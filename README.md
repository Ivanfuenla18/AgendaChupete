# 🍼 Agenda Chupete

> Digitalización segura, ágil y en tiempo real de la comunicación entre escuelas infantiles (0–3 años) y familias.

Proyecto intermodular del **CFGS Desarrollo de Aplicaciones Multiplataforma (DAM)** (curso 2026/27) en el **IES Gaspar Melchor de Jovellanos** (Fuenlabrada, Madrid), tutorizado por **Víctor Borja Martín Hernández**.

---

## 📋 Sobre el proyecto

Tradicionalmente, el seguimiento diario en el primer ciclo de educación infantil (0 a 3 años) se apoya en agendas en papel o comentarios verbales a la entrada y salida. Este sistema dificulta reaccionar rápido ante incidencias o falta de material, consume tiempo valioso de los educadores y carece de trazabilidad segura en las autorizaciones de recogida.

**Agenda Chupete** resuelve esto mediante un ecosistema multiplataforma con enfoque **B2B / SaaS** para escuelas infantiles, diseñado bajo criterios de seguridad y protección de datos conforme al **RGPD** y con control de acceso por roles (**RBAC**: `DIRECCION`, `EDUCADOR`, `FAMILIA`).

---

## ✨ Funcionalidades principales (MVP)

* **Perfil Educador (App Android):**
  * Registro individual o masivo del día a día del bebé (ingestas, horas de sueño, deposiciones, estado de ánimo y anécdotas).
  * Envío rápido de alertas de reposición de material (pañales, cremas, ropa de cambio).
  * Caché local para no perder registros ante microcortes de cobertura en el centro.
* **Perfil Familia (App Android):**
  * Consulta en tiempo real del parte diario y recepción de notificaciones push.
  * Envío de avisos de salud o medicación al centro.
  * Emisión de autorizaciones digitales para la recogida del menor con datos identificativos de la persona autorizada.
* **Panel de Gestión Web para Dirección:**
  * Alta de aulas, asignación de educadores, gestión de matrículas de alumnos y supervisión general del centro.
  * Exportación administrativa en CSV.
* **Backend y Base de Datos:**
  * API REST segura con autenticación mediante **JWT** y control de permisos por rol.
  * Modelo relacional estructurado para centros, aulas, educadores, alumnos, familias, registros diarios y autorizaciones.
* **Plan de Empresa y Viabilidad:**
  * Estudio de mercado, modelo de suscripción SaaS para guarderías, estimación de costes y estrategia de captación inicial.

---

## 🛠️ Stack tecnológico

| Capa / Ámbito | Tecnologías y herramientas |
| :--- | :--- |
| **Backend & API REST** | Node.js, TypeScript, Express, `jsonwebtoken`, `bcrypt`, `firebase-admin` |
| **Base de datos & ORM** | PostgreSQL, Prisma |
| **App Móvil Android** | Kotlin, Jetpack Compose, arquitectura MVVM, Retrofit, Room, Firebase SDK |
| **Panel Web Dirección** | React, TypeScript, Vite, Tailwind CSS, Axios |
| **Notificaciones push** | Firebase Cloud Messaging (FCM) |
| **DevOps, pruebas y despliegue** | Git, GitHub, GitHub Projects, Postman, Docker, Docker Compose, Railway, Vercel |
| **Negocio y análisis** | Google Sheets, Google Forms |

---

## 🚀 Posibles ampliaciones (Post-MVP)

* **Galería multimedia segura y anuario digital:** almacenamiento privado en Firebase Storage con URLs firmadas temporales, marcas de agua desde Node.js y medidas frente a capturas en Android.
* **Traducción automática de comunicaciones:** integración de **DeepL API** desde el backend para facilitar partes y avisos a familias de distintos idiomas.
* **Control de acceso mediante código QR o firma biométrica:** generación y lectura de códigos QR temporales en Android con **Google ML Kit** vinculados a las autorizaciones de recogida en PostgreSQL.

---

## 🏗️ Arquitectura general

```text
[ App Android (Kotlin + Compose + Retrofit + Room) ] ──┐
                                                      ├──► [ API REST (Node.js + TypeScript + Express + JWT) ] ──► [ PostgreSQL (Prisma) ]
[ Panel Web Dirección (React + Vite + Tailwind) ] ────┘                 │
                                                                       ▼
                                                        [ Firebase Cloud Messaging (FCM) ]
```
## 🏫 Contexto académico
Centro: IES Gaspar Melchor de Jovellanos (Fuenlabrada, Madrid)

Ciclo: CFGS Desarrollo de Aplicaciones Multiplataforma (Curso 2026/27)

Profesor tutor: Víctor Borja Martín Hernández
