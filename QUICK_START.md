# ⚡ Quick Start - 5 Minutos

Se você quer começar AGORA, siga este guia rápido.

## 📋 Pré-requisitos (Já Instalados?)

- ✅ Node.js 18+ (`node --version`)
- ✅ Android Studio com emulador
- ✅ Expo CLI (`npm install -g expo-cli`)

## 🚀 Começar em 5 Passos

### 1️⃣ Instalar Dependências (2 min)

```bash
cd rotaverde
npm install
```

### 2️⃣ Iniciar Backend (Terminal 1)

```bash
cd src/backend
npm install
node server.js
```

**Você verá:**
```
🚀 Backend running on http://localhost:3001
```

### 3️⃣ Iniciar Expo (Terminal 2)

```bash
# Na raiz do projeto
npm start
```

### 4️⃣ Abrir no Emulador

```
Pressione: a
```

### 5️⃣ Usar o App

- **Login:** `teste@exemplo.com` / `123456`
- **Explorar:** Clique em "Explorar" para ver parques
- **Marcar:** Clique no ❤️ para marcar como visitado
- **Fotos:** Clique "Adicionar Foto" para compartilhar

## 🎯 Pronto!

Se chegou aqui, tudo está funcionando! 🎉

Para mais detalhes, leia:
- `README.md` - Documentação completa
- `INSTALACAO_DETALHADA.md` - Guia passo a passo

## 🆘 Algo Deu Errado?

### Backend não conecta

```bash
# Verificar se está rodando
curl http://localhost:3001/health

# Se não funcionar, verifique:
# 1. Terminal 1 ainda está aberto?
# 2. Porta 3001 está disponível?
# 3. Firewall não está bloqueando?
```

### App não abre

```bash
# Pressione 'r' no terminal do Expo para recarregar
# Ou pressione 'c' para limpar cache
```

### Emulador lento

- Feche outros programas
- Reinicie o emulador
- Use um dispositivo com menos RAM na configuração

---

**Dúvidas? Leia `INSTALACAO_DETALHADA.md`**
