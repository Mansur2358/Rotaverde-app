# 📱 Guia Completo de Instalação - RotaVerde

Este guia detalha todos os passos para rodar o RotaVerde no seu computador com Android Studio.

## 🎯 Objetivo Final

Você terá:
- ✅ Projeto React Native rodando localmente
- ✅ Backend Node.js em `http://localhost:3001`
- ✅ App funcionando no emulador Android
- ✅ Câmera, localização e fotos funcionando

## 📋 Pré-requisitos

### 1. Node.js e npm

**Windows:**
1. Acesse [nodejs.org](https://nodejs.org/)
2. Baixe a versão LTS (recomendado)
3. Execute o instalador
4. Aceite os termos e siga as instruções

**Verificar instalação:**
```bash
node --version    # Deve mostrar v18.x.x ou superior
npm --version     # Deve mostrar 9.x.x ou superior
```

### 2. Android Studio

**Windows:**
1. Acesse [developer.android.com/studio](https://developer.android.com/studio)
2. Baixe Android Studio
3. Execute o instalador
4. Durante a instalação, marque:
   - ✅ Android SDK
   - ✅ Android SDK Platform
   - ✅ Android Virtual Device (AVD)

**Após instalação:**
```bash
# Adicionar Android SDK ao PATH (Windows)
# Variáveis de Ambiente → ANDROID_HOME → C:\Users\[seu_usuario]\AppData\Local\Android\Sdk
```

### 3. Expo CLI

```bash
npm install -g expo-cli

# Verificar
expo --version    # Deve mostrar versão
```

## 🚀 Instalação Passo a Passo

### Passo 1: Preparar o Projeto

```bash
# 1. Extrair o ZIP (se necessário)
# Clique com botão direito → Extrair para...

# 2. Abrir terminal na pasta do projeto
# Windows: Shift + Clique direito → Abrir PowerShell aqui
# Mac/Linux: Abrir Terminal e cd para a pasta

cd rotaverde
```

### Passo 2: Instalar Dependências

```bash
# Instalar todas as dependências do projeto
npm install

# Isso pode levar 5-10 minutos
# Você verá muitas linhas de output - é normal!

# Após terminar, você verá:
# added XXX packages in XXs
```

**Se der erro:**
```bash
# Limpar cache e tentar novamente
npm cache clean --force
npm install
```

### Passo 3: Configurar Variáveis de Ambiente

```bash
# Copiar arquivo de exemplo
cp .env.example .env

# Editar .env (opcional para desenvolvimento)
# Deixar como está está OK para começar
```

### Passo 4: Criar Emulador Android

1. **Abrir Android Studio**
2. **Ir para Device Manager:**
   - Menu superior → Tools → Device Manager
   
3. **Criar novo dispositivo:**
   - Clique em "Create Virtual Device"
   - Selecione "Pixel 4" (ou outro)
   - Clique "Next"
   - Selecione "API 34" (ou versão recente)
   - Clique "Next"
   - Clique "Finish"

4. **Iniciar emulador:**
   - Na lista de dispositivos, clique no botão ▶️ (Play)
   - Aguarde 1-2 minutos para iniciar

### Passo 5: Iniciar Backend (Terminal 1)

```bash
# Abrir um terminal/PowerShell NOVO
# Navegar para a pasta do backend
cd rotaverde
cd src/backend

# Instalar dependências do backend
npm install

# Iniciar servidor
node server.js

# Você verá:
# 🚀 Backend running on http://localhost:3001
# 📱 Make sure your Android emulator is configured to access localhost:3001

# DEIXAR ESTE TERMINAL ABERTO!
```

### Passo 6: Iniciar Expo (Terminal 2)

```bash
# Abrir OUTRO terminal/PowerShell
# Navegar para raiz do projeto
cd rotaverde

# Iniciar Expo
npm start

# Você verá um menu:
# ┌─────────────────────────────────────────────────────────────┐
# │                                                             │
# │   ✔ Metro Bundler ready                                    │
# │                                                             │
# │  › Press a to open Android                                 │
# │  › Press i to open iOS simulator                           │
# │  › Press w to open web                                     │
# │  › Press r to reload app                                   │
# │  › Press m to toggle menu                                  │
# │                                                             │
# └─────────────────────────────────────────────────────────────┘

# DEIXAR ESTE TERMINAL ABERTO!
```

### Passo 7: Conectar ao Emulador

```bash
# No terminal do Expo (Terminal 2), pressione: a

# Aguarde alguns segundos...
# O app deve abrir automaticamente no emulador Android!

# Se não abrir, tente:
# 1. Pressione 'r' para recarregar
# 2. Verifique se o emulador está rodando
# 3. Verifique se o backend está rodando (Terminal 1)
```

## ✅ Verificar se Está Funcionando

### Checklist

- [ ] Backend rodando em Terminal 1 (porta 3001)
- [ ] Expo rodando em Terminal 2
- [ ] Emulador Android aberto
- [ ] App RotaVerde aberto no emulador
- [ ] Tela de Login visível

### Testar Funcionalidades

1. **Login:**
   - Email: `teste@exemplo.com`
   - Senha: `123456`
   - Clique em "Entrar"

2. **Explorar Parques:**
   - Clique na aba "Explorar"
   - Você deve ver uma lista de parques

3. **Marcar como Visitado:**
   - Clique em um parque
   - Clique no ícone de coração
   - Vá para "Visitados" e confirme

4. **Adicionar Foto:**
   - No detalhe do parque, clique "Adicionar Foto"
   - Clique "Tirar Foto" ou "Escolher da Galeria"
   - Selecione uma imagem
   - Clique "Enviar Foto"

## 🔧 Comandos Úteis

### Recarregar App

```bash
# No terminal do Expo, pressione: r
```

### Limpar Cache

```bash
# Parar Expo (Ctrl+C)
npm start -- --clear

# Ou
expo start -c
```

### Resetar Projeto

```bash
# Parar tudo (Ctrl+C em ambos terminais)

# Limpar dependências
rm -rf node_modules
npm install

# Reiniciar
npm start
```

### Verificar Porta 3001

```bash
# Windows (PowerShell)
netstat -ano | findstr :3001

# Mac/Linux
lsof -i :3001

# Se estiver em uso, mude a porta em .env
```

## 🐛 Problemas Comuns

### Problema: "Cannot find module 'expo'"

**Solução:**
```bash
npm install expo
npm install
```

### Problema: Emulador não consegue acessar backend

**Verificar:**
1. Backend está rodando? (Terminal 1)
2. Porta 3001 está aberta?
3. Firewall está bloqueando?

**Solução Windows:**
```bash
# Adicionar exceção no Firewall
# Windows Defender Firewall → Permitir app através do firewall
# Procure por Node.js e marque
```

### Problema: "Metro bundler failed"

**Solução:**
```bash
# Parar Expo (Ctrl+C)
npm cache clean --force
npm start -- --clear
```

### Problema: Emulador muito lento

**Solução:**
1. Feche outros programas
2. Use emulador com menos RAM (Device Manager → Editar → RAM: 2GB)
3. Ative aceleração de hardware (Device Manager → Editar → Graphics: Hardware)

### Problema: Permissões de câmera negadas

**Solução:**
1. No emulador, abra Settings
2. Apps → RotaVerde → Permissions
3. Câmera → Permitir
4. Galeria → Permitir
5. Localização → Permitir

## 📱 Estrutura de Pastas Importante

```
rotaverde/
├── src/
│   ├── app/           ← Código principal do app
│   ├── features/      ← Funcionalidades (auth, parks, gallery)
│   └── backend/       ← Servidor Node.js
├── package.json       ← Dependências do app
├── app.json          ← Configuração Expo
└── README.md         ← Documentação
```

## 🎓 Próximos Passos

Após ter tudo funcionando:

1. **Explorar o código:**
   - Abra `src/app/App.tsx` para entender a estrutura
   - Veja `src/features/parks/screens/ParkListScreen.tsx` para exemplo de tela

2. **Fazer mudanças:**
   - Edite um arquivo
   - Salve (Ctrl+S)
   - Pressione 'r' no Expo para recarregar

3. **Adicionar funcionalidades:**
   - Siga o padrão das pastas `features/`
   - Crie nova pasta em `src/features/[nome]/`
   - Adicione screens, hooks e services

## 📞 Suporte Rápido

| Problema | Comando |
|----------|---------|
| App travado | Pressione 'r' no Expo |
| Quer reiniciar | Pressione 'c' no Expo |
| Ver logs | Pressione 'j' no Expo |
| Sair | Pressione 'q' no Expo |

## ✨ Dicas Importantes

1. **Sempre deixe dois terminais abertos:**
   - Terminal 1: Backend (`node server.js`)
   - Terminal 2: Expo (`npm start`)

2. **Emulador deve estar ligado:**
   - Abra Android Studio
   - Clique no botão Play do dispositivo

3. **Primeira vez é mais lenta:**
   - Primeira execução pode levar 2-3 minutos
   - Próximas vezes são mais rápidas

4. **Salve o arquivo e recarregue:**
   - Edite código
   - Salve (Ctrl+S)
   - Pressione 'r' no Expo

---

**Parabéns! 🎉 Você está pronto para desenvolver com RotaVerde!**

Se tiver dúvidas, consulte o `README.md` ou a seção Troubleshooting acima.
