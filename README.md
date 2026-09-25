# LP · Cardápio Metrificado Click

Página curta de venda direta, feita para receber o tráfego do criativo UGC.

**Oferta:** Cardápio Metrificado por R$ 39,90, pagamento único, 30 dias de acesso.

**Fluxo:** vídeo UGC → `index.html` → botão "Quero metrificar meu cardápio por R$ 39,90" → checkout do gateway → cliente → dados no CRM → oferta das soluções maiores da Click.

## Arquivos

- `index.html`: a LP curta (é essa que vai no anúncio).
- `completa.html`: a versão longa, com diagnóstico interativo e seções extras, guardada para a próxima etapa.

## Interação

A calculadora da Click IA fica ao lado do texto (no celular, entre o texto e o botão de compra). A pessoa digita preço, custo e vendas de um prato e escolhe a meta de CMV. A página mostra o CMV, se está acima da meta, o preço ou custo que resolve e o valor por mês. A conta roda no navegador; nada é enviado.

## Configuração

No fim do `index.html`, edite:

```js
var CONFIG = {
  checkoutUrl: "",   // link de pagamento único de R$ 39,90 criado no gateway
  price: "R$ 39,90"
};
```

Sem `checkoutUrl`, o botão mostra um aviso de prévia.

As UTMs do anúncio (`utm_source`, `utm_campaign`...), `fbclid`/`gclid` e a headline vista (`lp_headline`) são repassadas para o link do checkout.

## Headlines A/B

Use `?h=1`, `?h=2` ou `?h=3` no link do anúncio.

1. Seu cardápio pode estar vendendo prejuízo. *(padrão)*
2. Você sabe quanto realmente sobra em cada prato que vende?
3. Quanto dinheiro seu restaurante está deixando na mesa?

## Eventos (Google Tag Manager)

`headline_view`, `calc_used` e `checkout_click` (com a informação se a pessoa usou a calculadora), enviados para `window.dataLayer`.

## Publicar no GitHub Pages

1. Suba os arquivos no repositório.
2. Em **Settings → Pages**, escolha a branch `main` e a pasta `/ (root)`.
3. A página fica em `https://SEU-USUARIO.github.io/NOME-DO-REPO/`.
