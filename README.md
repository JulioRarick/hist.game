# Hist.Game - Quiz Interativo de História da África

<div align="center">

[🇵🇧 Português](#português) | [🇺🇸 English](#english)

</div>

---

## Português

### 📚 Sobre o Projeto

**Hist.Game** é uma aplicação web interativa desenvolvida em **Next.js 14** que oferece quizzes educacionais sobre história da África, com foco em personagens e civilizações importantes como o **Reino de Cuxe** e as **Candaces**.

Este projeto combina educação e gamificação para proporcionar uma experiência de aprendizado envolvente e divertida sobre tópicos históricos importantes do continente africano.

### ✨ Funcionalidades

- ✅ **Quizzes Interativos**: Questões verdadeiro/falso sobre história da África
- ✅ **Múltiplos Temas**: Diferentes quizzes sobre civilizações e personagens históricos
- ✅ **Sistema de Pontuação**: Calcula e exibe resultados em tempo real
- ✅ **Interface Responsiva**: Design moderno adaptado para desktop e mobile
- ✅ **Animações Suaves**: Efeitos visuais com Framer Motion
- ✅ **Design Acessível**: Componentes da Radix UI com foco em acessibilidade
- ✅ **Temas Históricos Visuais**: Cada quiz tem um tema visual próprio
- ✅ **Página Sobre**: Informações sobre o projeto
- ✅ **Página de Resultados**: Exibição detalhada dos resultados do quiz

### 🎮 Quizzes Disponíveis

1. **Kush (Cuxe)** - Quizzes sobre o antigo Reino de Cuxe
2. **Candaces** - Questões sobre as importantes líderes do Reino de Cuxe
3. **Em Desenvolvimento** - Mais temas serão adicionados em breve

### 🛠️ Tecnologias Utilizadas

#### Frontend
- **Next.js 14.2.7** - Framework React com renderização no servidor
- **React 18** - Biblioteca JavaScript para interfaces
- **TypeScript 5** - Tipagem estática para JavaScript
- **Tailwind CSS 3.4.1** - Framework CSS utilitário
- **Framer Motion 11.5.4** - Biblioteca de animações
- **Radix UI** - Componentes acessíveis primitivos
- **Lucide React** - Ícones SVG modernos

#### Ferramentas de Desenvolvimento
- **pnpm** - Gerenciador de pacotes rápido
- **ESLint** - Linter JavaScript/TypeScript
- **Prettier** - Formatador de código
- **Tailwind CSS Animate** - Extensão de animações CSS

### 📁 Estrutura do Projeto

```
hist.game/
├── src/
│   ├── app/                    # Aplicação Next.js
│   │   └── (app)/
│   │       ├── (home)/         # Página inicial
│   │       ├── about/          # Página sobre
│   │       └── games/          # Página de quizzes
│   │           └── quiz/       # Páginas de quiz por tema
│   ├── components/             # Componentes React reutilizáveis
│   │   ├── animated-div.tsx
│   │   ├── footer.tsx
│   │   ├── header.tsx
│   │   ├── navbar-item.tsx
│   │   └── ui/                 # Componentes de UI
│   ├── contexts/               # Context API do React
│   │   └── quiz-context-provider.tsx
│   ├── data/                   # Dados dos quizzes
│   │   ├── data-questionnaire-candaces.ts
│   │   ├── data-questionnaire-kush.ts
│   │   └── @types/
│   │       └── data-quiz.ts
│   ├── hooks/                  # Custom hooks
│   │   └── useQuiz.tsx
│   ├── lib/                    # Utilitários
│   │   └── utils.ts
│   └── styles/                 # Estilos globais
│       └── globals.css
├── public/                     # Arquivos estáticos
│   └── images/
├── package.json
├── tsconfig.json
├── tailwind.config.ts
├── postcss.config.mjs
├── next.config.mjs
├── prettier.config.cjs
└── components.json             # Configuração do Shadcn UI
```

### 🚀 Como Executar

#### Pré-requisitos
- **Node.js** 18+ ou superior
- **pnpm** (recomendado) ou npm

#### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/JulioRarick/hist.game.git
cd hist.game
```

2. Instale as dependências:
```bash
pnpm install
# ou
npm install
```

3. Execute o servidor de desenvolvimento:
```bash
pnpm dev
# ou
npm run dev
```

4. Abra [http://localhost:3000](http://localhost:3000) no seu navegador

### 📝 Scripts Disponíveis

```bash
# Desenvolvimento
pnpm dev          # Inicia servidor de desenvolvimento

# Build
pnpm build        # Cria build otimizado para produção
pnpm start        # Inicia servidor de produção

# Qualidade de Código
pnpm lint         # Executa ESLint para verificar erros

# Formatação
prettier --write . # Formata código com Prettier
```

### 🎨 Temas Visuais

Cada quiz possui um tema visual único baseado nas cores e motivos culturais:

- **Kush**: Tema inspirado na civilização do antigo Cuxe
- **Candaces**: Tema com cores ricas representando o poder das líderes históricas

### 📊 Status da Build

✅ **Produção**: Build compilada com sucesso
- Todas as rotas pré-renderizadas como conteúdo estático
- Nenhum erro de ESLint ou TypeScript
- Otimizações de imagem aplicadas

### 🔄 Atualizações Recentes

- ✅ Instalação completa de dependências
- ✅ Build de produção validada
- ✅ Verificação de linting concluída
- ✅ Testes de compilação TypeScript aprovados
- ✅ Documentação README atualizada (português e inglês)

### ⚙️ Recomendações para Produção

1. Instale o pacote `sharp` para otimização de imagens:
   ```bash
   pnpm add -D sharp
   ```

2. Atualize o banco de dados browserslist:
   ```bash
   npx update-browserslist-db@latest
   ```

### 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se livre para:
- Reportar bugs
- Sugerir novas funcionalidades
- Enviar pull requests com melhorias

### 📄 Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.

### 👨‍💻 Autor

**Julio Rarick** - [GitHub](https://github.com/JulioRarick)

---

## English

### 📚 About the Project

**Hist.Game** is an interactive web application developed in **Next.js 14** that offers educational quizzes about African history, focusing on important characters and civilizations such as the **Kingdom of Kush** and the **Candaces**.

This project combines education and gamification to provide an engaging and fun learning experience about important historical topics from the African continent.

### ✨ Features

- ✅ **Interactive Quizzes**: True/false questions about African history
- ✅ **Multiple Themes**: Different quizzes about historical civilizations and characters
- ✅ **Scoring System**: Calculates and displays results in real-time
- ✅ **Responsive Interface**: Modern design adapted for desktop and mobile
- ✅ **Smooth Animations**: Visual effects with Framer Motion
- ✅ **Accessible Design**: Radix UI components with accessibility focus
- ✅ **Visual Historical Themes**: Each quiz has its own visual theme
- ✅ **About Page**: Information about the project
- ✅ **Results Page**: Detailed display of quiz results

### 🎮 Available Quizzes

1. **Kush** - Quizzes about the ancient Kingdom of Kush
2. **Candaces** - Questions about the important leaders of the Kingdom of Kush
3. **Coming Soon** - More themes will be added soon

### 🛠️ Technologies Used

#### Frontend
- **Next.js 14.2.7** - React framework with server-side rendering
- **React 18** - JavaScript library for interfaces
- **TypeScript 5** - Static typing for JavaScript
- **Tailwind CSS 3.4.1** - Utility-first CSS framework
- **Framer Motion 11.5.4** - Animation library
- **Radix UI** - Accessible primitive components
- **Lucide React** - Modern SVG icons

#### Development Tools
- **pnpm** - Fast package manager
- **ESLint** - JavaScript/TypeScript linter
- **Prettier** - Code formatter
- **Tailwind CSS Animate** - CSS animation extension

### 📁 Project Structure

```
hist.game/
├── src/
│   ├── app/                    # Next.js application
│   │   └── (app)/
│   │       ├── (home)/         # Home page
│   │       ├── about/          # About page
│   │       └── games/          # Quizzes page
│   │           └── quiz/       # Quiz pages by theme
│   ├── components/             # Reusable React components
│   │   ├── animated-div.tsx
│   │   ├── footer.tsx
│   │   ├── header.tsx
│   │   ├── navbar-item.tsx
│   │   └── ui/                 # UI components
│   ├── contexts/               # React Context API
│   │   └── quiz-context-provider.tsx
│   ├── data/                   # Quiz data
│   │   ├── data-questionnaire-candaces.ts
│   │   ├── data-questionnaire-kush.ts
│   │   └── @types/
│   │       └── data-quiz.ts
│   ├── hooks/                  # Custom hooks
│   │   └── useQuiz.tsx
│   ├── lib/                    # Utilities
│   │   └── utils.ts
│   └── styles/                 # Global styles
│       └── globals.css
├── public/                     # Static files
│   └── images/
├── package.json
├── tsconfig.json
├── tailwind.config.ts
├── postcss.config.mjs
├── next.config.mjs
├── prettier.config.cjs
└── components.json             # Shadcn UI configuration
```

### 🚀 How to Run

#### Prerequisites
- **Node.js** 18+ or higher
- **pnpm** (recommended) or npm

#### Installation

1. Clone the repository:
```bash
git clone https://github.com/JulioRarick/hist.game.git
cd hist.game
```

2. Install dependencies:
```bash
pnpm install
# or
npm install
```

3. Run the development server:
```bash
pnpm dev
# or
npm run dev
```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

### 📝 Available Scripts

```bash
# Development
pnpm dev          # Start development server

# Build
pnpm build        # Create optimized production build
pnpm start        # Start production server

# Code Quality
pnpm lint         # Run ESLint to check for errors

# Formatting
prettier --write . # Format code with Prettier
```

### 🎨 Visual Themes

Each quiz has a unique visual theme based on cultural colors and patterns:

- **Kush**: Theme inspired by the ancient Kush civilization
- **Candaces**: Theme with rich colors representing the power of historical leaders

### 📊 Build Status

✅ **Production**: Build compiled successfully
- All routes pre-rendered as static content
- No ESLint or TypeScript errors
- Image optimizations applied

### 🔄 Recent Updates

- ✅ Complete dependency installation
- ✅ Production build validated
- ✅ Linting check completed
- ✅ TypeScript compilation tests passed
- ✅ README documentation updated (Portuguese and English)

### ⚙️ Production Recommendations

1. Install the `sharp` package for image optimization:
   ```bash
   pnpm add -D sharp
   ```

2. Update the browserslist database:
   ```bash
   npx update-browserslist-db@latest
   ```

### 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Send pull requests with improvements

### 📄 License

This project is licensed under the MIT License. See the LICENSE file for more details.

### 👨‍💻 Author

**Julio Rarick** - [GitHub](https://github.com/JulioRarick)

---

<div align="center">

**Made with ❤️ by Julio Rarick**

</div>
