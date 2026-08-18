# LADTEC — Apresentação, Marca e Templates

Site estático da Liga Acadêmica de Direito e Tecnologia. Quatro páginas em abas: apresentação da liga, diretriz de marca, arquivos de logotipo e templates.

Não há build, dependência de Node nem gerador de site. É HTML, CSS e JavaScript puros — basta servir a pasta.

## Publicar no GitHub Pages

### Opção A — pelo navegador, sem usar Git

1. Crie um repositório novo em <https://github.com/new>. Se quiser o endereço `https://SEU-USUARIO.github.io`, o repositório precisa se chamar exatamente `SEU-USUARIO.github.io`. Qualquer outro nome funciona também, e o endereço fica `https://SEU-USUARIO.github.io/nome-do-repo/`.
2. Marque o repositório como **Public** (o Pages em conta gratuita só publica repositório público).
3. Na página do repositório, clique em **Add file → Upload files** e arraste **o conteúdo desta pasta** — `index.html`, `.nojekyll` e a pasta `assets`. Não arraste a pasta que contém tudo; o `index.html` precisa ficar na raiz do repositório.
4. Clique em **Commit changes**.
5. Vá em **Settings → Pages**. Em *Source*, escolha **Deploy from a branch**; em *Branch*, escolha `main` e a pasta `/ (root)`. Salve.
6. Aguarde de um a dois minutos. O endereço aparece no topo da mesma tela.

### Opção B — pela linha de comando

```bash
cd caminho/para/esta/pasta
git init
git add .
git commit -m "Site LADTEC v2.1"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/NOME-DO-REPO.git
git push -u origin main
```

Depois, ative o Pages em **Settings → Pages** como no passo 5 acima.

## Estrutura

```
index.html                          página única com as quatro abas
.nojekyll                           desliga o Jekyll no GitHub Pages
assets/
  img/logo/                         PNG do logotipo, fundo transparente
  img/referencias/                  estudos iniciais de aplicação
  img/thumbs/                       miniaturas dos templates
  downloads/                        .docx e .pptx para download
```

## O que precisa ser conferido antes de divulgar o endereço

A página de apresentação contém dados de exemplo, sinalizados no próprio texto:

- instituição de vínculo e nome de quem orienta
- periodicidade dos encontros, número de membros, processo seletivo
- contadores em `00` e o e-mail `contato@ladtec.org`

Corrija tudo isso no `index.html` antes de compartilhar o link. Uma busca por `00` e por `ladtec.org` encontra os pontos.

## Como editar

- **Textos:** abra o `index.html` em qualquer editor e altere direto no HTML.
- **Cores e fontes:** estão declaradas uma única vez no bloco `:root`, no topo do arquivo. Alterar ali propaga para tudo.
- **Trocar um arquivo baixável:** substitua o arquivo dentro de `assets/downloads/` mantendo o mesmo nome; nada mais precisa mudar.
- **Adicionar um documento novo:** coloque o arquivo em `assets/downloads/`, a miniatura em `assets/img/thumbs/` e duplique um bloco `<figure class="doc">` na aba correspondente.

## Dependências externas

O botão de download das artes (Instagram, slide, certificado, capa de paper) usa a biblioteca `html-to-image`, carregada de CDN. **Ela precisa de internet na primeira visita.** O restante do site — inclusive os downloads de `.docx`, `.pptx` e PNG — funciona offline.

As fontes Instrument Serif, Inter e JetBrains Mono vêm do Google Fonts. Sem internet, o navegador cai para as substituições declaradas no CSS (Georgia e a sans do sistema), e o layout continua legível.

## Licença dos ativos

O logotipo, a paleta e os textos são da LADTEC. As fontes são de licença aberta: Instrument Serif e Inter sob SIL Open Font License, JetBrains Mono sob Apache 2.0.
