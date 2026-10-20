# ObdovaSuite

Suite de aplicaciones de gestión para gestorías y pymes.

## 📦 Aplicaciones

### GestorPro (v1)
Plataforma multi-tenant de gestión documental y contable para gestorías.

**Features:**
- Portal cliente para subida documentos
- Dashboard gestoría con bandeja unificada
- OCR + IA para extracción automática facturas
- Conciliación bancaria asistida con IA
- Sistema multi-tenant (SaaS)

---

## 🛠️ Stack Tecnológico

### Backend
- **.NET 10.0** (LTS)
- **Entity Framework Core 10.0**
- **SQL Server 2022** (Docker)
- **ASP.NET Core Identity** + JWT
- **SignalR** (Real-time)
- **Hangfire** (Background jobs)

### Frontend
- **Angular 22.2**
- **Tailwind CSS 4.0**
- **Spartan UI** + **PrimeNG 19**
- **Lucide Icons**

### IA/OCR
- **Azure AI Document Intelligence**
- **Claude API (Anthropic)**

### Infraestructura
- **Docker Compose** (SQL Server, Redis, Seq)
- **Azure** (Producción)

---

## 🚀 Setup Desarrollo

### Prerequisitos

```bash
.NET SDK 10.0.402+
Node.js 24.x LTS
Angular CLI 22.x
Docker Desktop 29.x
```

### Instalación

1. **Clonar repo:**
```bash
git clone https://github.com/ubedaWP/ObdovaSuite.git
cd ObdovaSuite
```

2. **Levantar servicios Docker:**
```bash
docker compose up -d
```

3. **Restaurar dependencias backend:**
```bash
cd src/GestorPro.API
dotnet restore
```

4. **Aplicar migraciones DB:**
```bash
dotnet ef database update
```

5. **Instalar dependencias frontend:**
```bash
cd ../GestorPro.Web
npm install
```

6. **Ejecutar aplicación:**

**Backend (Terminal 1):**
```bash
cd src/GestorPro.API
dotnet run
# API: https://localhost:7001
# Swagger: https://localhost:7001/swagger
```

**Frontend (Terminal 2):**
```bash
cd src/GestorPro.Web
ng serve
# App: http://localhost:4200
```

---

## 🗄️ Base de Datos

**Connection String (Development):**

Server=localhost,1433;Database=GestorProDB;User Id=sa;Password=YourStrong!Passw0rd;TrustServerCertificate=True;


**Acceso SQL Server:**
- Host: `localhost`
- Port: `1433`
- User: `sa`
- Password: `YourStrong!Passw0rd`

**Herramientas recomendadas:**
- Azure Data Studio
- SQL Server Management Studio
- DBeaver

---

## 📊 Servicios Docker

| Servicio | Puerto | URL | Credenciales |
|----------|--------|-----|--------------|
| SQL Server | 1433 | localhost:1433 | sa / YourStrong!Passw0rd |
| Redis | 6379 | localhost:6379 | - |
| Seq (Logs) | 5341 | http://localhost:5341 | - |

---

## 🏗️ Estructura Proyecto

ObdovaSuite/
├── src/
│ ├── GestorPro.API/ # ASP.NET Core Web API
│ ├── GestorPro.Core/ # Domain entities & interfaces
│ ├── GestorPro.Application/ # Business logic & services
│ ├── GestorPro.Infrastructure/ # Data access & external services
│ └── GestorPro.Web/ # Angular 22 SPA
├── tests/
│ ├── GestorPro.Tests.Unit/
│ └── GestorPro.Tests.Integration/
├── docker-compose.yml
├── .gitignore
└── README.md


---

## 🧪 Testing

### Unit Tests
```bash
cd tests/GestorPro.Tests.Unit
dotnet test
```

### Integration Tests
```bash
cd tests/GestorPro.Tests.Integration
dotnet test
```

### E2E Tests (Playwright)
```bash
cd src/GestorPro.Web
npm run e2e
```

---

## 📝 Convenciones

### Git Commits

feat(scope): descripción corta
fix(scope): descripción corta
docs(scope): descripción corta
refactor(scope): descripción corta
test(scope): descripción corta


**Ejemplos:**
```bash
git commit -m "feat(auth): add JWT authentication"
git commit -m "feat(clients): add clients CRUD API"
git commit -m "fix(auth): resolve token expiration issue"
```

### Branching

main # Código en producción
develop # Desarrollo activo
feature/* # Nuevas features
bugfix/* # Bug fixes
hotfix/* # Fixes urgentes producción


---

## 🔐 Secrets Management

**NUNCA commitear:**
- `appsettings.Development.json`
- `appsettings.Production.json`
- API keys
- Connection strings reales

**Usar:**
- `appsettings.json` (valores placeholder)
- User Secrets (desarrollo local)
- Azure Key Vault (producción)

---

## 📚 Documentación

- [Architecture Decision Records](/docs/adr/)
- [API Documentation](/docs/api/)
- [Database Schema](/docs/database/)
- [Deployment Guide](/docs/deployment/)

---

## 👥 Contribuidores

- **David** - Desarrollo Full Stack

---

## 📄 Licencia

Privado - Todos los derechos reservados

---

## 🐛 Issues & Feedback

Para reportar bugs o sugerencias, crear issue en GitHub.