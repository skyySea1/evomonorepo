# Criação de projetos novos

crie uma pasta no projeto e adicione ela na pasta pnpm-workspaces.yaml
as dependências devem apontar para o pnpm-workspace.yaml, e todos os projetos contidos serão detectados recursivamente, para impoortar basta.

Exemplo:
Adicione o projeto/pacote desejado no package.json
```json
  "ui": "workspace:*"
```
assim poderá importar direto: ´import { Button } from 'ui'´

Funcionamento:
pnpm-workspace
    |_apps -> projetos detectados recursivamente no workspace raiz
        |_ App_web -> projetos que podem ser importados atribuindo um json 
        |_ Backend
    Packages
        |_ UI

# convenções
Usar Vite + Vue3 + TypeScript opcional.
Habilitar lint, format e testes (ESLint + Prettier + Vitest).
Usar lazy-loading para rotas e manualChunks no Vite para otimizar chunking.
Configurar CI para rodar pnpm install --frozen-lockfile e pnpm run build.
não usar pnpm update



pnpm --prod, -P prepaara para produção nãoo instalando dev dependencies
```tree -L 3```paara ver a estrutura de pastas

[motivos para usar o vue-devtools](https://devtools.vuejs.org/getting-started/introduction)