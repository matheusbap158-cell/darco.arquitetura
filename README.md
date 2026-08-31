# D'Arco Arquitetura — Landing page

Estúdio de arquitetura em Lavras, MG. Página única em HTML/CSS/JS, sem dependências
nem etapa de build: abra `index.html` no navegador.

## Estrutura

| Caminho | O que é |
|---|---|
| `index.html` | A página inteira — marcação, estilos e scripts em um arquivo |
| `Fotos/` | Renders dos projetos |
| `Logo/` | Logotipo (**arquivo com problema — ver abaixo**) |
| `Modern_house_pool_at_dusk_*.mp4` | Vídeo de fundo do hero |
| `Materiais Desing System/` | Design system que rege cores, tipografia e componentes |
| `Estrutura de sessões e Texto.txt` | Copy aprovado, usado palavra por palavra |
| `serve.mjs` | Servidor estático opcional, só para pré-visualizar |

## Pré-visualizar

```bash
node serve.mjs
```

Depois abra `http://localhost:4321`.

## Decisões técnicas

- **Sem bibliotecas.** Único recurso externo: Cormorant Garamond e Manrope
  via Google Fonts, as duas famílias que o design system especifica.
- **Vídeo do hero** só carrega em telas ≥768px e sem preferência por movimento
  reduzido — são 3,5 MB que não descem no celular. A foto serve de plano base.
- **Botão de pausa** no vídeo: a WCAG 2.2.2 exige controle para movimento
  automático com mais de 5 segundos.
- **Menu mobile** aplica `inert` no restante da página enquanto aberto, para o
  foco de teclado não vazar por trás do painel.
- **Tratamento fotográfico** por filtro CSS: os renders de luz diurna fria
  recebem correção quente, para uniformizar com os de fim de tarde.

## Pendências antes de publicar

1. **Logotipo.** `Logo/Editedimage_1788170363921.png` tem 0% de pixels
   transparentes — é um logo branco achatado sobre o quadriculado que representa
   transparência. Não é utilizável. O cabeçalho e o rodapé usam um lockup
   tipográfico provisório, marcado com `PROVISÓRIO` no HTML. Substituir por PNG
   com canal alfa ou SVG, e reativar o `<link rel="icon">`.
2. **Dados fictícios.** Buscar `data-ficticio` no HTML (9 ocorrências): número de
   projetos, cidades atendidas e os nomes/metragens de dois projetos. *High
   Garden* é real — o nome aparece na fachada dos renders.
3. **35+ anos** vem da bio do Instagram, não de fonte interna. Confirmar.
4. **`[E-mail]`** no rodapé e o **depoimento**, mantidos como placeholder de
   propósito: o copy determina que depoimento inventado quebra a confiança.
5. **Imagens.** ~22 MB de PNG. Converter para WebP/AVIF antes de ir ao ar.
