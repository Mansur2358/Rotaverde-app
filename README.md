# RotaVerde - Guia de Parques Nacionais

Um aplicativo React Native com Expo para explorar parques nacionais brasileiros, marcar visitados e compartilhar fotos de suas aventuras.

## 📱 Sobre o Projeto

**RotaVerde** é um aplicativo mobile desenvolvido com:

- **React Native** - Framework para desenvolvimento mobile
- **Expo** - Plataforma para desenvolvimento React Native
- **TypeScript** - Tipagem estática
- **Express.js** - Backend Node.js
- **MySQL** - Banco de dados
- **React Navigation** - Navegação entre telas
- **Expo Camera** - Integração com câmera
- **Expo Image Picker** - Seleção de imagens
- **Expo Location** - Serviços de localização

## 🚀 Instalação Rápida

### Pré-requisitos

Antes de começar, certifique-se de ter instalado:

1. **Node.js 18+** - [Download](https://nodejs.org/)
2. **npm ou yarn** - Vem com Node.js
3. **Android Studio** - [Download](https://developer.android.com/studio)
4. **Expo CLI** - `npm install -g expo-cli`

### Passo 1: Clonar/Extrair o Projeto

```bash
# Se estiver em um ZIP, extraia primeiro
unzip rotaverde.zip
cd rotaverde
```

### Passo 2: Instalar Dependências

```bash
# Instalar todas as dependências
npm install

# Ou com yarn
yarn install
```

### Passo 3: Configurar Variáveis de Ambiente

```bash
# Copiar arquivo de exemplo
cp .env.example .env

# Editar .env com suas configurações (opcional para desenvolvimento)
# nano .env  (ou use seu editor preferido)
```

### Passo 4: Iniciar o Backend (Terminal 1)

```bash
# Navegar para o backend
cd src/backend

# Instalar dependências do backend (se necessário)
npm install

# Iniciar o servidor
node server.js

# Você verá:
# 🚀 Backend running on http://localhost:3001
```

### Passo 5: Iniciar o Expo (Terminal 2)

```bash
# Na raiz do projeto
npm start

# Ou com yarn
yarn start
```

Você verá um menu com opções:

```
› Press a to open Android
› Press i to open iOS simulator
› Press w to open web
› Press r to reload app
› Press m to toggle menu
```

## 📱 Rodar no Emulador Android Studio

### Opção 1: Usar Expo Go (Mais Rápido)

1. **Instalar Expo Go** no emulador:
   - Abra Android Studio
   - Inicie o emulador
   - Abra o Google Play Store
   - Busque "Expo Go" e instale

2. **Conectar ao Expo**:
   - No terminal onde rodou `npm start`, pressione `a`
   - O app abrirá automaticamente no emulador

### Opção 2: Build APK (Mais Complexo)

```bash
# Gerar APK para teste
eas build --platform android --local

# Depois instalar no emulador
adb install path/to/app.apk
```

## 🏗️ Estrutura do Projeto

```
rotaverde/
├── src/
│   ├── app/
│   │   ├── navigation/          # Navegação entre telas
│   │   │   └── AppNavigator.tsx
│   │   ├── providers/           # Context Providers
│   │   │   ├── AuthProvider.tsx
│   │   │   ├── LocationProvider.tsx
│   │   │   └── ParksProvider.tsx
│   │   └── App.tsx              # App principal
│   │
│   ├── features/
│   │   ├── auth/                # Autenticação
│   │   │   ├── screens/
│   │   │   │   ├── LoginScreen.tsx
│   │   │   │   └── RegisterScreen.tsx
│   │   │   └── hooks/
│   │   │       └── useAuth.ts
│   │   │
│   │   ├── parks/               # Parques
│   │   │   ├── screens/
│   │   │   │   ├── ParkListScreen.tsx
│   │   │   │   ├── ParkDetailScreen.tsx
│   │   │   │   ├── VisitedParksScreen.tsx
│   │   │   │   └── AddPhotoScreen.tsx
│   │   │   └── hooks/
│   │   │       └── useParks.ts
│   │   │
│   │   └── gallery/             # Galeria de Fotos
│   │       ├── screens/
│   │       │   ├── MyPhotosScreen.tsx
│   │       │   └── PhotoDetailScreen.tsx
│   │       └── hooks/
│   │           └── useGallery.ts
│   │
│   ├── backend/                 # Backend Express
│   │   └── server.js
│   │
│   └── assets/                  # Imagens e ícones
│       ├── images/
│       └── icons/
│
├── app.json                     # Configuração Expo
├── package.json                 # Dependências
├── tsconfig.json               # Configuração TypeScript
├── .env.example                # Variáveis de exemplo
└── README.md                   # Este arquivo
```

## 🎯 Funcionalidades Principais

### 1. **Explorar Parques**
- Listar todos os parques nacionais
- Buscar por nome
- Filtrar por tipo (montanha, floresta, praia)
- Visualizar detalhes completos

### 2. **Parques Visitados**
- Marcar parques como visitados
- Manter lista de favoritos
- Sincronizar com conta do usuário

### 3. **Galeria de Fotos**
- Tirar fotos com câmera
- Selecionar fotos da galeria
- Fazer upload de fotos
- Deletar fotos
- Editar informações de fotos

### 4. **Autenticação**
- Login com email/senha
- Registro de novo usuário
- Suporte para Google Login (configurável)
- Sessão persistente

### 5. **Localização**
- Obter localização do usuário
- Calcular distância até parques
- Mostrar parques próximos

## 📦 Dependências Principais

| Pacote | Versão | Descrição |
|--------|--------|-----------|
| expo | ^50.0.0 | Plataforma React Native |
| react-native | ^0.73.0 | Framework mobile |
| react-navigation | ^6.1.9 | Navegação entre telas |
| expo-camera | ^14.1.0 | Acesso à câmera |
| expo-image-picker | ^14.7.1 | Seleção de imagens |
| expo-location | ^16.5.5 | Serviços de localização |
| axios | ^1.6.2 | Cliente HTTP |
| express | ^4.18.2 | Framework backend |
| mysql2 | ^3.6.5 | Driver MySQL |

## 🔧 Configuração do Android Studio

### Criar Emulador

1. Abra Android Studio
2. Vá para **AVD Manager** (Tools → Device Manager)
3. Clique em **Create Virtual Device**
4. Selecione um dispositivo (ex: Pixel 4)
5. Selecione uma API (ex: API 34)
6. Clique em **Finish**

### Iniciar Emulador

```bash
# Listar dispositivos disponíveis
adb devices

# Iniciar emulador específico
emulator -avd <nome_do_emulador>
```

### Acessar Backend Local

O emulador precisa acessar o backend rodando em `localhost:3001`. Use este IP especial:

```
http://10.0.2.2:3001  # Para emulador Android padrão
```

Este IP já está configurado no projeto. Se precisar mudar, edite:
- `src/app/providers/AuthProvider.tsx`
- `src/app/providers/ParksProvider.tsx`

## 🐛 Troubleshooting

### "Cannot find module 'expo'"

```bash
npm install expo
```

### "Emulador não consegue acessar backend"

1. Certifique-se que o backend está rodando:
   ```bash
   curl http://localhost:3001/health
   ```

2. Use o IP correto no código:
   ```
   http://10.0.2.2:3001  # Para emulador Android
   ```

3. Verifique firewall:
   ```bash
   # Windows
   netstat -ano | findstr :3001
   
   # Mac/Linux
   lsof -i :3001
   ```

### "Permissões de câmera negadas"

1. Abra Settings no emulador
2. Vá para Apps → RotaVerde
3. Permissões → Câmera → Permitir

### "Erro ao instalar dependências"

```bash
# Limpar cache
npm cache clean --force

# Reinstalar
rm -rf node_modules package-lock.json
npm install
```

## 📝 Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
# Backend
PORT=3001
NODE_ENV=development

# Database (opcional, backend usa mock data por padrão)
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=
DB_NAME=rotaverde

# API
API_URL=http://10.0.2.2:3001

# Google Maps (opcional)
GOOGLE_MAPS_API_KEY=your_key_here
```

## 🚀 Deployment

### Build para Android

```bash
# Gerar APK de produção
eas build --platform android

# Ou localmente
eas build --platform android --local
```

### Publicar no Expo

```bash
# Login no Expo
expo login

# Publicar
expo publish
```

## 📚 Recursos Úteis

- [React Native Docs](https://reactnative.dev/)
- [Expo Docs](https://docs.expo.dev/)
- [React Navigation](https://reactnavigation.org/)
- [Android Studio Guide](https://developer.android.com/studio)
- [Expo Camera](https://docs.expo.dev/versions/latest/sdk/camera/)
- [Expo Location](https://docs.expo.dev/versions/latest/sdk/location/)

## 🤝 Contribuindo

Sinta-se livre para fazer fork, criar branches e enviar pull requests!

## 📄 Licença

Este projeto é fornecido como está para fins educacionais.

## 📞 Suporte

Se encontrar problemas:

1. Verifique o terminal para mensagens de erro
2. Consulte a seção Troubleshooting
3. Verifique se todas as dependências estão instaladas
4. Tente limpar cache: `npm cache clean --force`

---

**Desenvolvido com ❤️ para explorar parques nacionais**

Versão: 1.0.0  
Última atualização: Novembro 2025
