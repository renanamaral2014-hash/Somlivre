# SomLivre — protótipo web

Interface em estilo Spotify para pesquisar no YouTube, colar links de vídeos e montar uma fila de reprodução.

## Testar
Abra `index.html` em um navegador com internet. O player oficial do YouTube e a busca dependem de conexão.

## Publicar e instalar no iPhone
1. Publique os arquivos em um host HTTPS estático (por exemplo, GitHub Pages ou Netlify).
2. No iPhone, abra o endereço publicado no Safari.
3. Toque em Compartilhar → Adicionar à Tela de Início.

## Limitações importantes
- A busca encaminha para os resultados oficiais do YouTube; não extrai nem baixa áudio.
- A reprodução usa o player incorporado oficial. Alguns vídeos não permitem incorporação.
- O iOS/Safari e as regras do YouTube controlam a reprodução em segundo plano. Este protótipo não contorna YouTube Premium e não garante que o áudio continue com a tela bloqueada.
- Para reprodução de áudio em segundo plano confiável em iOS, é necessário usar uma fonte de áudio que autorize isso e implementar os recursos de mídia apropriados; um player web não pode garantir esse comportamento para vídeos do YouTube.
