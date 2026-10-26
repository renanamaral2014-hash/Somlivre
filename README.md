# SomLivre v2 — Player de música pessoal (PWA)

Aplicativo web instalável no iPhone com **biblioteca própria**, **fila de reprodução** e foco em **continuar tocando com a tela bloqueada**.

## O que mudou em relação à v1

| Antes (v1) | Agora (v2) |
|------------|------------|
| Só YouTube incorporado | Biblioteca local com arquivos de áudio reais |
| Áudio parava ao bloquear a tela | Usa `<audio>` + **Media Session API** (controles na tela de bloqueio) |
| Sem armazenamento | **IndexedDB** guarda suas músicas no aparelho |
| Interface básica | UI escura moderna, abas, barra de player fixa, progresso |
| Manifest incompleto | PWA completa com ícones, `standalone`, service worker |

## Funcionalidades

- **Biblioteca**: adicione MP3, M4A, AAC, WAV, OGG, FLAC do seu iPhone/computador.
- **Fila**: toque, adicione à fila, pule faixas.
- **Player**: play/pausa, anterior/próxima, barra de progresso clicável.
- **Tela bloqueada**: o iOS deve mostrar título, artista e controles (via Media Session).
- **YouTube (secundário)**: busca abre o YouTube oficial; dá para colar link e incorporar (sem garantia de segundo plano).
- **Instalável**: Adicionar à Tela de Início no Safari.

## Como publicar no GitHub Pages

1. Crie um repositório (ou use o que já tem) e envie **todos** os arquivos desta pasta para a raiz (ou para a branch `gh-pages` / pasta `docs`, conforme sua configuração).
2. Em **Settings → Pages**, escolha a branch e a pasta corretas.
3. Aguarde alguns minutos e abra o endereço `https://SEU-USUARIO.github.io/NOME-DO-REPO/`.

Arquivos obrigatórios:

```
index.html
manifest.json
sw.js
icon-192.png
icon-512.png
README.md
```

## Como instalar no iPhone

1. Abra o link **no Safari** (não no Chrome).
2. Toque no botão **Compartilhar**.
3. Escolha **Adicionar à Tela de Início**.
4. Confirme. O ícone do SomLivre aparece na home.

Usar como PWA (tela cheia) melhora a chance de o áudio continuar em segundo plano.

## Limitações importantes (honestidade)

- **YouTube embutido** continua sujeito às regras do YouTube e do iOS: muitas vezes o áudio **para** ao bloquear a tela. Por isso a biblioteca local é o caminho principal.
- Os arquivos ficam **só no seu aparelho** (IndexedDB). Não há sincronização em nuvem nesta versão.
- Adicione apenas músicas que você tem autorização para usar.
- Em alguns casos o Safari ainda pede interação do usuário antes do primeiro `play()` (política de autoplay).

## Testar localmente

Qualquer servidor estático serve. Exemplos:

```bash
# Python
python3 -m http.server 8080

# Node
npx serve .
```

Abra `http://localhost:8080` no navegador. No iPhone use o endereço da rede ou publique via Pages.

## Próximos passos possíveis

- Integração com API do YouTube (com sua própria API key) para busca de resultados na interface.
- Armazenamento em nuvem (ex.: Google Drive / Dropbox / Firebase) para sincronizar a biblioteca.
- Playlists nomeadas e ordenação.
- Equalizador ou modo aleatório.

---

Feito para ser simples de publicar e o mais próximo possível de um app de música de verdade no iPhone, sem backend complexo.
