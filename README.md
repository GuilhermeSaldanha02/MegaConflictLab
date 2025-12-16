# 🧪 MegaConflictLab – Gitflow com 12 Branches em Colisão

## 📋 Objetivo do Exercício

Este laboratório foi criado para **forçar conflitos reais e simultâneos na branch `staging`**, simulando um **time grande**, com múltiplas features alterando **os mesmos arquivos críticos**.

Neste exercício você irá praticar:

- Gitflow em ambiente caótico  
- Conflitos múltiplos no mesmo arquivo  
- Consolidação manual de configurações  
- Refatoração pós-merge  
- Tomada de decisão técnica  
- Mentalidade de Integrador / Tech Lead  

⚠️ **Aviso:** este projeto foi feito para quebrar várias vezes. Isso é intencional.

---

## 🎯 Público-Alvo

- Estudantes de Git intermediário e avançado  
- Desenvolvedores em formação  
- Quem deseja dominar conflitos de merge em staging  

---

## 🏗️ Estrutura Inicial do Projeto

```
project/
├── config/
│   └── system.config.json
├── src/
│   ├── core/
│   │   └── app.js
│   ├── services/
│   │   └── logger.js
│   └── features/
│       └── README.md
└── README.md
```

---

## 📄 Arquivo Base – config/system.config.json

```json
{
  "appName": "MegaConflictLab",
  "version": "1.0.0",
  "environment": "staging"
}
```

---

## 📄 Arquivo Base – src/core/app.js

```javascript
function startApp() {
    console.log("Sistema iniciado");
}

startApp();
```

---

## 🎭 As 12 Branches (Equipes)

Todas as branches partem da `main`  
Todas alteram **os mesmos arquivos propositalmente**

| Branch | Feature |
|------|--------|
| feat/auth | Autenticação |
| feat/users | Usuários |
| feat/payments | Pagamentos |
| feat/orders | Pedidos |
| feat/products | Produtos |
| feat/stock | Estoque |
| feat/shipping | Frete |
| feat/notifications | Notificações |
| feat/analytics | Analytics |
| feat/settings | Configurações |
| feat/security | Segurança |
| feat/logging | Logs |

---

## 🚀 RODADA 1 – Criação das Branches

```bash
git checkout main
git checkout -b staging

git checkout -b feat/auth
git checkout -b feat/users
git checkout -b feat/payments
git checkout -b feat/orders
git checkout -b feat/products
git checkout -b feat/stock
git checkout -b feat/shipping
git checkout -b feat/notifications
git checkout -b feat/analytics
git checkout -b feat/settings
git checkout -b feat/security
git checkout -b feat/logging
```

---

## 🧩 RODADA 2 – Implementações (INTENCIONALMENTE CONFLITANTES)

Cada branch deve editar:

- `config/system.config.json`  
- `src/core/app.js`  

### feat/auth

```json
"auth": { "jwt": true, "expiration": 3600 }
```

```javascript
console.log("Auth carregado");
```

---

### feat/users

```json
"users": { "profile": true, "avatar": true }
```

```javascript
console.log("Users carregados");
```

---

### feat/payments

```json
"payments": { "provider": "stripe", "currency": "BRL" }
```

```javascript
console.log("Payments carregados");
```

---

### feat/orders

```json
"orders": { "autoApprove": false }
```

```javascript
console.log("Orders carregados");
```

---

### feat/products

```json
"products": { "categories": true }
```

```javascript
console.log("Products carregados");
```

---

### feat/stock

```json
"stock": { "control": true }
```

```javascript
console.log("Stock carregado");
```

---

### feat/shipping

```json
"shipping": { "calculator": "default" }
```

```javascript
console.log("Shipping carregado");
```

---

### feat/notifications

```json
"notifications": { "email": true, "sms": false }
```

```javascript
console.log("Notifications carregadas");
```

---

### feat/analytics

```json
"analytics": { "enabled": true }
```

```javascript
console.log("Analytics carregado");
```

---

### feat/settings

```json
"settings": { "darkMode": true }
```

```javascript
console.log("Settings carregados");
```

---

### feat/security

```json
"security": { "rateLimit": true }
```

```javascript
console.log("Security carregado");
```

---

### feat/logging

```json
"logging": { "level": "debug" }
```

```javascript
console.log("Logging carregado");
```

---

## 🔥 RODADA 3 – Merge Caótico em Staging

```
git merge feat/auth
git merge feat/users
git merge feat/payments
git merge feat/orders
git merge feat/products
git merge feat/stock
git merge feat/shipping
git merge feat/notifications
git merge feat/analytics
git merge feat/settings
git merge feat/security
git merge feat/logging
```

💥 **Conflitos esperados em:**

- `config/system.config.json`  
- `src/core/app.js`  

---

## 🧠 RODADA 4 – Resolução dos Conflitos

### ✅ Resultado Esperado – system.config.json

```json
{
  "appName": "MegaConflictLab",
  "version": "1.0.0",
  "environment": "staging",
  "auth": { "jwt": true, "expiration": 3600 },
  "users": { "profile": true, "avatar": true },
  "payments": { "provider": "stripe", "currency": "BRL" },
  "orders": { "autoApprove": false },
  "products": { "categories": true },
  "stock": { "control": true },
  "shipping": { "calculator": "default" },
  "notifications": { "email": true, "sms": false },
  "analytics": { "enabled": true },
  "settings": { "darkMode": true },
  "security": { "rateLimit": true },
  "logging": { "level": "debug" }
}
```

---

### ✅ Resultado Esperado – src/core/app.js

```javascript
function startApp() {
    console.log("Auth carregado");
    console.log("Users carregados");
    console.log("Payments carregados");
    console.log("Orders carregados");
    console.log("Products carregados");
    console.log("Stock carregado");
    console.log("Shipping carregado");
    console.log("Notifications carregadas");
    console.log("Analytics carregado");
    console.log("Settings carregados");
    console.log("Security carregado");
    console.log("Logging carregado");
}

startApp();
```

---

## 🏁 Finalização

```bash
git add .
git commit -m "merge(staging): resolve conflitos das 12 features"
```

---

## 🎯 Aprendizados Esperados

- Resolver conflitos múltiplos no mesmo arquivo  
- Consolidar grandes arquivos de configuração  
- Refatorar código após merge  
- Pensar como integrador de sistemas  
- Dominar conflitos em staging  
