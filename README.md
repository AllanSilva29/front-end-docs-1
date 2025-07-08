# Guia para Adicionar Conteúdo - Starlight (Astro)

Este README fornece instruções sobre como adicionar novo conteúdo a este repositório, que utiliza o Starlight. A pasta principal para o conteúdo do site é a `website/`.

## Estrutura de Pastas Principal

O conteúdo do site que será publicado no GitHub Pages está localizado dentro da pasta `website/`. A estrutura relevante dentro de `website/` é:

```
website/
├── public/             # Ativos estáticos (favicons, etc.)
├── src/
│   ├── assets/         # Imagens
│   ├── content/
│   │   ├── docs/       # Arquivos Markdown para as páginas de documentação
│   │   └── config.ts   # Configuração do Starlight
└── astro.config.mjs    # Configuração do Astro
```

## Adicionando Novas Páginas de Conteúdo

Para adicionar novas páginas à documentação:

1.  Navegue até a pasta `website/src/content/docs/`.
2.  Crie um novo arquivo com a extensão `.md` (Markdown) ou `.mdx` (MDX, Markdown com componentes JSX).
3.  O nome do arquivo determinará a rota da página. Por exemplo, `nova-pagina.md` será acessível em `front-end-docs-1/nova-pagina`.
4.  Você pode organizar o conteúdo em subpastas dentro de `website/src/content/docs/` para criar seções aninhadas. Por exemplo, `website/src/content/docs/guia/parte-1.md` será acessível em `front-end-docs-1/guia/parte-1`.

## Adicionando Imagens

Para adicionar imagens que serão usadas nas suas páginas de documentação:

1.  Coloque os arquivos de imagem na pasta `website/src/public/`.
2.  No seu arquivo Markdown, você pode referenciar a imagem usando um caminho relativo a partir da pasta `src/public/`.

    Exemplo em Markdown:
    ```markdown
    ![Texto alternativo da imagem](/front-end-docs-1/nome-da-sua-imagem.png)
    ```
    *`front-end-docs-1` é o nome do repositório que está configurado no astro.config.mjs, todos os links devem partir dele.*

## Deploy para GitHub Pages

O site é automaticamente construído e implantado no GitHub Pages através de uma GitHub Action definida em `.github/workflows/deploy.yml`. Esta ação está configurada para:

*   Observar pushes para a branch `main`.
*   Construir o projeto Astro localizado na pasta `website/`.
*   Implantar o resultado na sua página do GitHub Pages.

Nenhuma ação manual de deploy é necessária após o push para a branch `main`, desde que a Action esteja configurada corretamente.

## Executando o Projeto Localmente

Para visualizar suas alterações localmente antes de fazer o push:

1.  **Navegue até a pasta do site:**
    ```bash
    cd website
    ```

2.  **Instale as dependências** (se for a primeira vez ou se as dependências mudaram):
    ```bash
    pnpm install
    ```

3.  **Inicie o servidor de desenvolvimento:**
    ```bash
    pnpm run dev
    ```
    Isso iniciará um servidor local (geralmente em `http://localhost:4321`) onde você poderá see seu site Starlight. O servidor recarregará automaticamente as alterações feitas nos arquivos de conteúdo.

## Contribuindo

Certifique-se de que suas alterações sejam testadas localmente antes de enviá-las para a branch `main`. Siga as convenções de nomenclatura de arquivos e estrutura de pastas para manter a organização do projeto.
