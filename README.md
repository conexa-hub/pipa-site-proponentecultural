# PIPA · Landing "Sou proponente"

Página de entrada da face **Proponente**. Arquivo único, sem build, sem dependência —
abre direto no navegador. A única coisa externa é a fonte, puxada do Google Fonts.

`index.html` é a versão atual. Vale guardar também a v1 no repositório se quiser
comparar: era a versão antes da faixa de pilares e da seção de incentivadores.

## Publicar no GitHub Pages

1. Subir `index.html` na raiz do repositório, branch `main`.
2. **Settings → Pages → Source:** *Deploy from a branch* · `main` · `/ (root)`.
3. Em cerca de um minuto sai em `https://<usuario>.github.io/<repo>/`.
4. Domínio próprio depois: **Settings → Pages → Custom domain** com `pipaprojetos.com.br`
   (ou um subdomínio), apontando o CNAME no registrador.

## Regras de marca — não improvisar aqui

Segue o **Manual de Marca v1.0 (jul/2026)**, paleta *Canindé & Tucano*. Os tokens estão
todos em `:root` no topo do arquivo. **Não usar hex solto fora dali.**

| Token | Hex | Trabalho |
|---|---|---|
| Noite | `#101C38` | Texto, header, fundo escuro |
| Canindé | `#1B4FD8` | Ação, link, progresso |
| Tucano | `#FF5C39` | Marca e meta batida — e só |
| Ouro | `#FFC21F` | Atenção e prazo |
| Folha | `#0B7A4C` | Conclusão |
| Névoa / Neve / Céu | `#F2F5FA` / `#F8FAFC` / `#E4EBFB` | Superfícies |
| Cinza | `#5A6879` | Texto secundário |

Três regras duras do manual, que a página respeita e que é fácil quebrar sem querer:

- **Um único ponto de tucano por tela.** Hoje são três, bem separados: o grifo do H1, o
  selo "meta batida" no painel financeiro e a faixa do Open Finance. Nunca dois na mesma
  rolagem.
- **Nunca tucano em botão de ação ao lado do azul.** CTA primário é sempre canindé.
- **Cor carrega só status, e todo status leva rótulo.** Nada comunicado apenas por cor.

Tipografia: **Familjen Grotesk**, pesos 400/600/700, tracking negativo crescendo com o
corpo. `tabular-nums` é obrigatório em qualquer valor monetário — já aplicado nas classes
de número.

## O símbolo animado

O SVG é reconstruído a partir da geometria do manual: retângulo maior a 45° com canto
arredondado em 16% do lado, corte de asa na diagonal (tucano em cima, canindé embaixo),
rabiola a 51% da altura saindo pela quina inferior direita.

A animação tem três camadas em velocidades diferentes — é isso que dá a leitura de vento:

1. `.cena-flutua` — sobe e desce 15px em 9s
2. `.heroi-corpo` — oscila cerca de 3° em 6,5s
3. `.heroi-rabiola` — mesma curva, **0,28s de atraso** e o dobro de amplitude

O atraso da rabiola é o detalhe que faz a coisa funcionar. Mexeu em um, mexe nos três.
A versão pequena do header usa `.pipa-corpo` / `.pipa-rabiola`, com amplitude menor.

## O que é placeholder

- Todos os `href="#"`: CTAs, login, links do rodapé e as faces "Sou incentivador" e
  "Sou organizador".
- O modal de vídeo tem um bloco marcado por comentário onde entra o `<iframe>`.
- Números do painel financeiro e dos exemplos são fictícios.
- Preço: R$ 49,90/mês por conta conectada vem do modelo de receita canônico. A linha
  "continua R$ 0" ainda não tem valor definido.

## Pendências conhecidas

- **SEO não foi feito.** Faltam title com palavra-chave, meta description, canonical,
  tags og: e JSON-LD de FAQPage e SoftwareApplication.
- **Analytics** não instalado.
- A seção de incentivadores não tem elemento visual, só cartões de texto.
- A promessa "extratos integrados automaticamente" depende de confirmar a cobertura de
  conta PJ em BB e Caixa com a Tecnospeed.

## Acessibilidade — já está no arquivo, favor não regredir

`prefers-reduced-motion` desliga toda a animação · foco visível no teclado · contraste
auditado com mínimo de 4,5:1 em texto · header fixo com `scroll-margin-top` nas âncoras ·
`<details>` nativo no FAQ · SVGs decorativos com `aria-hidden`.
