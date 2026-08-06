# Como usar

## 1. Estrutura
Suba esta pasta inteira (menos este arquivo, se quiser) como o repositório especial `draxxrlq/draxxrlq` — o repo com o mesmo nome do seu usuário é o que o GitHub renderiza automaticamente na página do perfil.

```
draxxrlq/
├── README.md
├── COMO_USAR.md          (pode apagar depois de ler)
├── assets/
│   ├── banner.svg
│   ├── hud.svg
│   ├── radar.svg
│   ├── ai-core.svg
│   ├── matrix.svg
│   ├── terminal.svg
│   ├── divider.svg
│   ├── footer.svg
│   └── background.svg
└── .github/
    └── workflows/
        └── snake.yml
```

## 2. Troque o usuário
Os links de estatísticas e o workflow usam `draxxrlq` como placeholder. Troque pelo seu usuário real do GitHub em:
- `README.md` → todos os `?username=draxxrlq` e `github.com/draxxrlq`
- `.github/workflows/snake.yml` já usa `${{ github.repository_owner }}` automaticamente, não precisa mexer

## 3. Ative o workflow da cobra (snake)
Depois do primeiro push, vá em **Settings → Actions → General → Workflow permissions** e marque **"Read and write permissions"**. Sem isso o workflow não consegue publicar `assets/snake.svg`. Depois rode o workflow uma vez manualmente em **Actions → generate snake → Run workflow**.

## 4. O que é 100% real e o que é aproximação
Sendo direto sobre os limites do GitHub Markdown, porque isso evita surpresa depois do deploy:

- **Funciona de verdade:** os SVGs animados (banner, HUD, radar, núcleo de IA, terminal, matrix, divisórias, rodapé) usam animação SMIL nativa do SVG — isso roda direto no navegador quando o GitHub exibe a imagem, sem precisar de CSS ou JS externo.
- **Não funciona no GitHub:** `<style>` embutido e a maioria dos atributos `style=""` são removidos pelo sanitizador de Markdown do GitHub. Por isso o "glassmorphism" (efeito de vidro fosco/blur) não é feito com CSS solto no README — ele é simulado dentro dos próprios SVGs (transparência + gradiente), e as seções de texto usam blocos de código (` ```yaml `) e tabelas para dar a estética de painel técnico.
- **Depende de serviço externo:** os badges (shields.io), as estatísticas (github-readme-stats, streak-stats, activity-graph) e a cobra (Platane/snk) são gerados por serviços de terceiros toda vez que alguém abre seu perfil — não são arquivos estáticos, então eles já "aprendem" a cor certa sozinhos a partir dos parâmetros na URL.

## 5. Personalize o conteúdo
Os textos de projetos, stack e "log de boot" no `README.md` foram escritos com base no que você mencionou (zap-bot, filtros com MediaPipe, quiz app, dados do Amazonas). Ajuste nomes de repositório, links e qualquer projeto novo que você quiser destacar.
