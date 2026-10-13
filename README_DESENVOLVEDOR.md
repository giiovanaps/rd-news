# RD NEWS — entrega para desenvolvimento

Portal regional de notícias de Porto Velho e Rondônia.

## O que está nesta cópia

- `dist/index.html`: aplicação completa em HTML, CSS e JavaScript.
- `dist/img/`: fotos usadas no portal (arquivos locais, sem dependência de servidores externos).
- `.openai/hosting.json`: identificação do projeto hospedado e diretório de publicação.
- `referencia/`: prancha visual com as versões desktop e mobile.
- `backup_original/`: versão anterior do `index.html`, fora da pasta publicada.

O projeto atual é estático e não depende de npm, framework ou banco de dados. CSS e JavaScript estão incorporados no `index.html`; as fontes (Newsreader e Libre Franklin) vêm do Google Fonts.

## Rodar localmente

Na raiz do projeto:

```bash
python3 -m http.server 8080 --directory dist
```

Depois, abrir:

```text
http://localhost:8080
```

## Estrutura e navegação

- Home: `#inicio` (âncoras internas: `#ultimas`, `#receba`, `#anuncie`, `#sobre`)
- Página de editoria: `#editoria/<chave>` (`cidade`, `politica`, `economia`, `saude`, `educacao`, `servico`, `cultura`, `esporte`, `opiniao`)
- Matéria: `#materia/<slug>`

Os dados ficam no JavaScript do `index.html`:

- `ED`: editorias (nome e descrição).
- `IMG`: fotos de `dist/img`, com texto alternativo e crédito exibido na legenda.
- `articles`: matérias e colunas (editoria, chamada, título, linha fina, data, hora, fonte, corpo, serviço, tags e relacionadas). O campo `short` é a versão curta do título usada em blocos menores.
- `MOST_READ` e `GALLERY`: listas de “Mais lidas” e “Porto Velho em imagens”.

A home, as editorias, a busca e a página de matéria são montadas a partir desses dados; a função `route()` controla a navegação por hash.

## Aviso de direitos

O projeto contém uma faixa superior e um popup de autoria da Flash Sites. O popup é exibido a cada 15 segundos por decisão do projeto. O texto e o intervalo podem ser localizados buscando por `rightsModal`, `rightsOpen` e `openRightsNotice`.

O layout, a identidade visual, a composição, o código e os elementos autorais devem ser tratados como material de uso reservado da Flash Sites para o RD NEWS. Consulte `DIREITOS_E_AUTORIA.md` antes de reutilizar, adaptar ou publicar qualquer parte.

## Conteúdo e imagens

O conteúdo atual foi montado como edição inicial e as matérias são reescritas editoriais com indicação de fonte dentro da própria página. Antes de colocar o portal em operação, a redação deve revisar autoria, atualização, política de correções, direitos de imagem e integração com um CMS.

As fotos de Porto Velho vêm do Wikimedia Commons (domínio público, CC0, CC BY e CC BY-SA — autor e licença aparecem na legenda de cada matéria e na galeria). Fotos genéricas (sala de aula, saúde, energia, lavoura e corrida) vêm do Unsplash e estão marcadas como ilustrativas. Previsão do tempo, colunistas e anúncios são conteúdo de demonstração. Para produção, usar fotos próprias ou de agência licenciada.

## SEO e operação

O `index.html` já possui title, description, keywords, Open Graph e theme-color. Uma versão de produção deve acrescentar sitemap, robots.txt, dados estruturados de notícia, URLs amigáveis e painel editorial.

## Publicação

O diretório configurado para publicação é `dist/`. O site hospedado atualmente é:

https://rd-news-porto-velho.nice-olive-1923.chatgpt.site

Nenhuma credencial de publicação foi incluída nesta cópia. O arquivo `.openai/hosting.json` contém apenas a configuração de identificação do projeto.

