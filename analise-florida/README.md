# Analise Florida

Landing page otimizada para tráfego pago para captação de brasileiros interessados em financiamento imobiliário na Flórida.

## Arquivos

- `index.html` — página principal para publicar na raiz do site/repositório.
- `analise.html` — cópia da mesma página para compatibilidade com URLs antigas ou campanhas que usem `/analise.html`.
- `assets/logo-acrisure-mortgage.png` — logo Acrisure Mortgage com fundo transparente.
- `assets/logo-equal-housing-lender.png` — logo Equal Housing Lender com fundo transparente/limpo.
- `assets/nilo-estrella.jpg` — foto profissional otimizada para web.

## Integração com CRM

A landing envia leads via POST JSON para:

```text
https://nexlead.duckdns.org/api/webhooks/analise-orlando
```

O endpoint mantém o nome `analise-orlando` para compatibilidade com o CRM atual, mas a copy da página é focada em Flórida.

## Rastreamento

A página captura automaticamente:

```text
gclid
gbraid
wbraid
campaign
adgroup
keyword
utm_source
utm_medium
utm_campaign
utm_content
utm_term
```

Após o envio bem-sucedido, dispara:

```js
dataLayer.push({ event: "lead_crm", ... })
```

Também dispara `gtag("event", "generate_lead", ...)` se uma Google tag já estiver instalada na página.

## WhatsApp

Não existe redirecionamento automático para WhatsApp nesta versão.

Fluxo:

```text
Lead preenche formulário
↓
Lead entra no CRM
↓
Contato manual pelo CRM
```

## Publicação no GitHub Pages

Para publicar como site novo:

1. Crie um repositório, por exemplo `analise-florida`.
2. Envie todos os arquivos deste projeto para a raiz do repositório.
3. Vá em `Settings > Pages`.
4. Em `Build and deployment`, selecione `Deploy from a branch`.
5. Escolha a branch `main` e pasta `/root`.
6. Salve e aguarde o GitHub Pages gerar a URL.

Para substituir a landing antiga:

1. Copie `index.html`, `analise.html` e a pasta `assets/` para o repositório atual da landing.
2. Se a URL antiga usava `/analise.html`, mantenha o arquivo `analise.html`.
3. Faça commit e push.
4. Teste o formulário com uma lead chamada `TESTE`.
5. Confirme se entrou no CRM.

## Compliance

A página contém:

- Nilo Estrella · Mortgage Loan Originator · NMLS #2802165
- Acrisure Mortgage, LLC · NMLS #152859
- Equal Housing Lender
- Link para NMLS Consumer Access
- Disclaimer reforçado

Recomenda-se validar o material com compliance/Acrisure antes de escalar investimento em mídia.
