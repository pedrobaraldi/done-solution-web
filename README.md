## Done Solutions Web

Aplicação web institucional da **Done Solutions**, construída com React + TypeScript e Vite.  
É uma landing page moderna, responsiva e animada, apresentando a empresa, serviços, operações, parceiros e canais de contato.

### Tecnologias principais

- **React 18** com **TypeScript**
- **Vite 5** (bundler e dev server)
- **React Router DOM** (roteamento SPA)
- **Tailwind CSS** + utilitários (`tailwind-merge`, `tailwindcss-animate`)
- **Framer Motion** (animações)
- **Radix UI + shadcn/ui** (componentes de UI)
- **@tanstack/react-query** (camada de dados, pronta para integrações)

### Estrutura de pastas (resumo)

- `src/`
  - `main.tsx` – ponto de entrada React, monta o `App` em `#root`
  - `App.tsx` – configura **React Router**, providers de UI, toasts e React Query
  - `pages/`
    - `index.tsx` – página principal, composta pelos blocos da landing
    - `NotFound.tsx` – página 404 genérica
  - `components/`
    - `Header.tsx` – cabeçalho com navegação e logo
    - `Hero.tsx` – seção hero com imagem de navio e call-to-action
    - `About.tsx` – bloco “Quem Somos” com métricas animadas
    - `Services.tsx` – apresentação dos serviços
    - `Operations.tsx` – explicação da operação, usando a imagem `polvo-operacao`
    - `Partners.tsx` – logotipos de clientes e órgãos reguladores
    - `Contact.tsx` – seção de contato (formulário / canais)
    - `Footer.tsx` – rodapé com logo branca e informações de fechamento
    - `WhatsAppButton.tsx` – botão flutuante para contato rápido via WhatsApp
    - `ui/` – componentes reutilizáveis (botões, tooltips, toasts etc.)
  - `assets/`
    - `logo.png`, `logo-branca.png`
    - `hero-shipping.jpg` (imagem principal do hero)
    - `polvo-operacao.png`
    - `clients/` – logotipos de clientes
    - `agencies/` – logotipos de agências reguladoras

- `public/`
  - `favicon.png` – favicon da aplicação (ilustração da baleia)

### Scripts disponíveis

Executar com **npm**, **pnpm** ou **bun** (conforme preferido). Abaixo, exemplos com `npm`:

- **Desenvolvimento**:

  ```bash
  npm install
  npm run dev
  ```

  O Vite exibirá no terminal o endereço (por padrão `http://localhost:5173`).

- **Build de produção**:

  ```bash
  npm run build
  ```

  Os arquivos otimizados ficam em `dist/`.

- **Preview do build**:

  ```bash
  npm run preview
  ```

- **Lint**:

  ```bash
  npm run lint
  ```

### Favicon

O favicon é configurado em `index.html` e usa o arquivo `public/favicon.png`, derivado da ilustração da baleia.  
Se quiser trocar o ícone, basta substituir `public/favicon.png` e manter a mesma referência no `<head>`:

```html
<link rel="icon" type="image/png" href="/favicon.png" />
```

### Como customizar conteúdo

- Textos principais (hero, quem somos, serviços, operações, parceiros, contato) podem ser editados diretamente nos componentes em `src/components/`.
- A ordem das seções da landing pode ser alterada em `src/pages/index.tsx`, que controla a composição da página principal.
- Para adicionar ou remover parceiros/agências, ajuste os imports e a lista em `Partners.tsx` e as imagens em `src/assets/clients` e `src/assets/agencies`.

### Deploy

O projeto gera uma SPA estática via `npm run build`, podendo ser publicada em:

- Serviços de hospedagem estática (Vercel, Netlify, GitHub Pages, Cloudflare Pages etc.)
- Servidor próprio (Nginx/Apache) servindo a pasta `dist/`

Certifique-se de configurar o servidor para redirecionar rotas para `index.html`, pois o projeto usa React Router.