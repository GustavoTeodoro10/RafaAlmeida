# Rafa Almeida | Fotógrafa Gestante Guarulhos

![Hero — Rafa Almeida Fotografia](assets/img/hero-preview.png)

---

## Estrutura de Arquivos

```
RafaAlmeida/
├── index.html              # Página principal (one-page)
├── 404.html                # Página de erro 404
├── robots.txt              # Regras para crawlers
├── sitemap.xml             # Sitemap (URL da prévia)
├── llms.txt                # Resumo do negócio para IAs
├── .gitignore
├── README.md
└── assets/
    ├── styles.css          # Tokens :root, animações, componentes
    ├── app.js              # Menu, scroll-reveal, carrossel, GoatCounter
    ├── tailwind-config.js  # Configuração do Tailwind CDN
    ├── hero.mp4            # Vídeo de fundo do hero
    └── img/
        ├── hero-preview.png        # Captura do hero (README)
        ├── og-image.jpg            # Open Graph / WhatsApp preview (1200×630)
        ├── favicon.svg             # Favicon SVG (prioridade em browsers modernos)
        ├── favicon.ico             # Favicon ICO (16/32/48px)
        ├── favicon-32.png          # Favicon PNG 32×32
        ├── favicon-512.png         # Favicon PNG 512×512
        ├── apple-touch-icon.png    # Apple Touch Icon 180×180
        ├── rafaela-retrato.jpg     # Foto da fotógrafa (seção Sobre)
        ├── gestante-pose-01.jpg    # Foto pose gestante
        ├── gestante-pose-02.jpg    # Foto pose gestante
        ├── servico-gestante.jpg    # Card serviço Aniversário
        ├── servico-feminino.jpg    # Card serviço Gestante
        ├── servico-aniversario.jpg # Card serviço Feminino
        ├── servico-familia.jpg     # Card serviço Família
        ├── servico-casal.jpg       # Card serviço Casal
        ├── servico-corporativo.jpg # Card serviço Corporativo
        └── galeria-01.jpg … galeria-20.jpg  # Galeria (20 fotos)
```

---

## Seções

| Seção | Âncora | Descrição |
|---|---|---|
| Hero | `#inicio` | Split layout — texto esquerda / vídeo direita |
| Diferencial | `#diferencial` | 3 pilares: Edição Elegante, Escuta Atenciosa, Memórias Únicas |
| Sobre | `#sobre` | Texto + retrato da fotógrafa |
| Serviços | `#servicos` | 6 cards com foto: Gestante, Aniversário, Família, Feminino, Casal, Corporativo |
| Galeria | `#galeria` | Carrossel infinito com 20 fotos (loop automático + drag) |
| FAQ | `#faq` | 6 perguntas frequentes em accordion |
| Localização | `#localizacao` | Endereço, telefone, Instagram + mapa Google embutido |
| CTA Final | `#contato` | Chamada de ação centrada com fundo escuro |
| Footer | — | Logo, contatos, links rápidos, crédito TeoCode |

---

## Tecnologia

- **HTML/CSS/JS puro** — sem build, sem backend, sem CMS
- **Tailwind CSS** via CDN (`tailwind-config.js` para tokens customizados)
- **Fontes:** Cormorant Garamond (display) + Outfit (corpo) via Google Fonts
- **Vídeo hero:** MP4 com `autoplay muted loop playsinline`
- **Carrossel:** loop infinito via `transform: translateX()` (RAF loop), drag habilitado
- **Analytics:** GoatCounter (sem cookies, sem banner)

---

## Design Tokens

```css
:root {
  --clr-bg:            #FAFAFA;
  --clr-bg-alt:        #F3F3F1;
  --clr-bg-dark:       #1A1817;
  --clr-bg-darker:     #131210;
  --clr-text:          #1C1A14;
  --clr-text-muted:    #6B6761;
  --clr-text-inverse:  #F5F3EF;
  --clr-accent:        #C06B4D;   /* terracota quente */
  --clr-accent-dark:   #9E5338;
  --font-display: 'Cormorant Garamond', Georgia, serif;
  --font-body:    'Outfit', system-ui, sans-serif;
  --radius:       4px;
  --ease-expo:    cubic-bezier(0.16,1,0.3,1);
  --transition:   0.28s var(--ease-expo);
}
```

---

## Deploy e GoatCounter

### Deploy gratuito

**GitHub Pages, Netlify ou Cloudflare Pages** — suba todos os arquivos na raiz do repositório.

```bash
# Exemplo com GitHub Pages
git init && git add . && git commit -m "site rafa almeida"
git remote add origin https://github.com/SEU_USUARIO/rafa-almeida.git
git push -u origin main
# → Habilitar Pages em Settings → Pages → main / root
```

### Domínio próprio

Após apontar o domínio:
1. Atualizar `canonical`, `og:url`, `twitter:image` e `sitemap.xml` para o domínio definitivo
2. **Remover** `<meta name="robots" content="noindex, nofollow">` de `index.html` e `404.html`
3. Enviar sitemap ao Google Search Console

### Lighthouse (mobile, localhost)

| Métrica | Nota |
|---|---|
| Performance | 61 |
| Acessibilidade | **100** |
| Boas Práticas | 81 |
| SEO | 69 |

> SEO 69 e Performance 61 são esperados em prévia: `noindex` intencional, sem HTTPS, Tailwind CDN (~360 KB). Resolvem no deploy definitivo.

### GoatCounter

Script no `<head>` de `index.html`:

```html
<script data-goatcounter="https://teocode.goatcounter.com/count"
        async src="//gc.zgo.at/count.js"></script>
```

**Eventos de CTA rastreados:**

| Evento | Localização |
|---|---|
| `cta-nav` | Navbar — botão "Agendar Sessão" |
| `cta-menu-mobile` | Menu mobile — botão "Agendar Sessão" |
| `cta-hero` | Hero — botão "Agendar Sessão" |
| `cta-sobre` | Seção Sobre — "Conversar no WhatsApp" |
| `cta-servicos-gestante` | Card Ensaio Gestante |
| `cta-servicos-aniversario` | Card Aniversário |
| `cta-servicos-familia` | Card Família |
| `cta-servicos-feminino` | Card Feminino |
| `cta-servicos-casal` | Card Casal |
| `cta-servicos-corporativo` | Card Corporativo |
| `cta-faq` | FAQ — "Tirar Dúvidas no WhatsApp" |
| `cta-localizacao` | Localização — "Agendar no Estúdio" |
| `cta-final` | CTA Final — "Agendar Minha Sessão" |
| `cta-footer` | Footer — ícone WhatsApp |
| `cta-footer-btn` | Footer — botão "Falar no WhatsApp" |
| `cta-flutuante` | Botão flutuante WhatsApp |

Para visualizar: **GoatCounter Dashboard → Events**.

> **Atenção:** o domínio precisa estar cadastrado no painel do GoatCounter para que os eventos apareçam.
