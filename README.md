# Nexora Systems — Landing Page

Landing page institucional da **Nexora Systems**, agência de desenvolvimento web sediada em Luanda/Panguila, Angola. Ficheiro único (`index.html`), sem build tools, pronto para deploy directo.

> 🔗 Ficheiro: `index.html` · 📍 Angola · 🎨 Identidade visual: preto + roxo · ✍️ Idioma: Português (pt-AO)

---

## 📋 Índice

1. [Visão geral](#-visão-geral)
2. [Stack tecnológica](#-stack-tecnológica)
3. [Estrutura do projecto](#-estrutura-do-projecto)
4. [Estrutura da página (secção a secção)](#-estrutura-da-página-secção-a-secção)
5. [Sistema de design](#-sistema-de-design)
6. [Como editar conteúdo](#-como-editar-conteúdo)
7. [Integração com WhatsApp](#-integração-com-whatsapp)
8. [Responsividade](#-responsividade)
9. [Animações e interações](#-animações-e-interações)
10. [Deploy](#-deploy)
11. [Checklist antes de publicar](#-checklist-antes-de-publicar)
12. [Placeholders que precisam de dados reais](#-placeholders-que-precisam-de-dados-reais)
13. [Acessibilidade](#-acessibilidade)
14. [Compatibilidade de navegadores](#-compatibilidade-de-navegadores)
15. [Histórico de alterações](#-histórico-de-alterações)
16. [Próximos passos sugeridos](#-próximos-passos-sugeridos)

---

## 🎯 Visão geral

Esta página substitui uma versão anterior que estava desenhada para um **produto SaaS de gestão de restaurantes** (PDV, mesas, QR code de menu). Foi reconvertida para apresentar a **Nexora Systems como agência**, cobrindo os serviços reais que a empresa presta:

- Sites institucionais
- Lojas online / e-commerce
- Sistemas web personalizados (PDV, marcações, painéis administrativos)
- Integração com WhatsApp (checkout, leads, notificações)
- Backend com Firebase (Firestore + Storage)
- Deploy e suporte contínuo

A página é uma **single-page** com navegação por âncoras (`#funcionalidades`, `#demo`, `#precos`, `#depoimentos`, `#demo-form`).

---

## 🛠 Stack tecnológica

| Camada | Tecnologia | Observações |
|---|---|---|
| Markup | HTML5 semântico | Um único ficheiro, `lang="pt-AO"` |
| Estilos | CSS puro (custom properties) | Sem framework CSS, sem pré-processador |
| Tipografia | Google Fonts — **Syne** (display) + **DM Sans** (corpo) | Carregadas via `<link>` no `<head>` |
| Ícones | Font Awesome 6.5.2 (CDN) | `fa-solid` e `fa-brands` |
| Interactividade | JavaScript vanilla (sem frameworks) | `IntersectionObserver`, eventos de scroll, `FormData` |
| Hospedagem recomendada | Vercel, Netlify ou Namecheap | Ficheiro estático, zero configuração de servidor |

Não há dependências de build (Webpack, Vite, npm). Basta abrir o ficheiro num browser ou fazer upload directo para qualquer hosting estático.

---

## 📁 Estrutura do projecto

```
index.html
├── <head>
│   ├── meta tags (charset, viewport)
│   ├── fontes Google (Syne, DM Sans)
│   ├── Font Awesome (CDN)
│   └── <style> ... todo o CSS embutido ... </style>
└── <body>
    ├── <nav>                     → navegação fixa com logo + CTA
    ├── <section class="hero">    → hero + mockup de dashboard
    ├── <div class="logos-band">  → clientes reais (marquee)
    ├── <section id="funcionalidades"> → grelha de serviços
    ├── <div class="logos-band">  → stack tecnológica (marquee)
    ├── <section id="demo">       → processo de trabalho + mockups
    ├── <section id="precos">     → 3 pacotes de preços
    ├── <section id="depoimentos"> → casos de clientes
    ├── <section id="demo-form">  → CTA final + formulário de lead
    ├── <footer>                  → rodapé
    ├── <a class="wa-btn">        → botão flutuante WhatsApp
    └── <script>                  → toda a lógica JS embutida
```

---

## 🧩 Estrutura da página (secção a secção)

### 1. Navbar (`<nav>`)
Fixa no topo, com blur de fundo. Logo "NEXORA SYSTEMS", links para secções e botão CTA "Pedir Orçamento".

### 2. Hero (`.hero`)
- Badge "Agência de desenvolvimento web em Angola"
- Título com destaque em gradiente ("modo digital")
- Subtítulo resumindo os serviços
- Dois CTAs: "Pedir orçamento" (primário) e "Ver o processo" (secundário)
- 3 estatísticas: projectos entregues, sectores atendidos, % deploy pronto para produção
- **Mockup de dashboard** (puro CSS/HTML, sem imagens): simula um painel administrativo com KPIs de projectos, gráfico de barras e um donut chart da stack usada

### 3. Faixa de clientes (`.logos-band`, 1ª ocorrência)
Marquee horizontal infinito (`@keyframes marquee`) com nomes de clientes reais: Grande Seba Lda, Fazenda Girassol, Canto da Engenharia, O Patrão Lounge & Bar, Barber Shop Panguila, A.M.P., Colégio Alfa e Ômega, Abel Costa Transportes.

### 4. Serviços (`#funcionalidades`)
Grelha de 6 cartões (`.features-grid`), cada um com ícone, título, descrição curta e tag:
1. Sites Institucionais
2. Lojas Online & E-commerce
3. Sistemas Web Personalizados
4. Integração WhatsApp
5. Backend & Base de Dados
6. Deploy & Suporte Contínuo

### 5. Faixa de stack tecnológica (`.logos-band`, 2ª ocorrência)
Segundo marquee, mais rápido (`animation-duration:16s`), listando: HTML5, CSS3, JavaScript, PHP, Node.js, Firebase, Bootstrap, GitHub, Vercel, Netlify.

### 6. Processo (`#demo`)
Layout de duas colunas:
- **Esquerda**: dois "screen mockups" sobrepostos — um simula uma lista de projectos em desenvolvimento, outro simula um QR code que leva ao WhatsApp
- **Direita**: lista numerada do processo de trabalho (briefing → identidade visual → desenvolvimento → deploy)

### 7. Preços (`#precos`)
3 cartões (`.pricing-grid`):
| Pacote | Preço de referência | Público |
|---|---|---|
| Site Institucional | a partir de 80.000 Kz | Sites simples, até 5 páginas |
| Loja Online / Sistema Web *(destaque)* | a partir de 180.000 Kz | E-commerce, painéis administrativos |
| Sistema Personalizado | sob medida | PDV, marcações, integrações à medida |

⚠️ **Estes valores são placeholders** — ver secção [Placeholders](#-placeholders-que-precisam-de-dados-reais).

### 8. Clientes (`#depoimentos`)
3 cartões descrevendo projectos reais (Grande Seba, A.M.P., Barber Shop Panguila) — descrições factuais dos projectos entregues, não citações literais dos clientes.

### 9. CTA final + formulário (`#demo-form`)
- Texto de fecho + selos de confiança (orçamento gratuito, entrega ágil, suporte contínuo, deploy pronto para produção)
- Formulário (`#lead-form`) com campos: nome, telefone, empresa/negócio, cidade, interesse (dropdown), mensagem
- Ao submeter, o JS monta uma mensagem formatada e abre o WhatsApp (`wa.me`) com o texto pré-preenchido — **não há backend nem envio de e-mail**, tudo acontece no cliente

### 10. Footer
Logo, copyright, links (Termos, Privacidade, Suporte, WhatsApp).

### 11. Botão flutuante do WhatsApp (`.wa-btn`)
Fixo no canto inferior direito, visível em toda a página.

---

## 🎨 Sistema de design

Definido em `:root` via CSS custom properties:

```css
--purple-1: #6C3BFF;   /* roxo principal — CTAs, destaques */
--purple-2: #8A5CFF;   /* roxo claro — hover, gradientes */
--purple-3: #4B1FCC;   /* roxo escuro — variação em gráficos */
--black:    #0A0A0B;   /* fundo base */
--dark:     #111113;   /* fundo secundário (mockups) */
--surface:  #16161A;   /* cartões */
--surface2: #1C1C22;   /* cartões em hover / topbar */
--border:        rgba(255,255,255,0.07);
--border-purple: rgba(108,59,255,0.3);
--text:   #FFFFFF;
--text-2: rgba(255,255,255,0.6);   /* texto secundário */
--text-3: rgba(255,255,255,0.35);  /* texto terciário / labels */
```

**Tipografia:**
- `Syne` (700/800) → títulos, logos, números de destaque
- `DM Sans` (300/400/500) → corpo de texto

**Padrões visuais:**
- Textura de ruído subtil sobreposta a toda a página (`body::before`, SVG `feTurbulence`)
- Cartões com hover que revela borda roxa (`border-color: var(--border-purple)`)
- Botões primários com `box-shadow` em glow roxo
- Efeito parallax suave em elementos com `.parallax-layer` + `data-parallax-speed`

Para alterar a cor de destaque de toda a página, basta editar as 3 variáveis `--purple-*` em `:root`.

---

## ✍️ Como editar conteúdo

| O que queres mudar | Onde procurar no `index.html` |
|---|---|
| Número de telefone / WhatsApp | Procurar por `244933609090` (aparece em ~5 sítios: CTA final, botão flutuante, footer, JS) |
| Textos do hero | `<section class="hero">` |
| Lista de clientes (marquee) | `<div class="logos-label">Clientes que confiam...` |
| Serviços oferecidos | `<section ... id="funcionalidades">` → `.feature-card` |
| Stack tecnológica exibida | segundo `.logos-band`, logo antes de `<!-- DEMO SECTION -->` |
| Passos do processo | `<section ... id="demo">` → `.demo-list` |
| Preços e pacotes | `<section ... id="precos">` → `.pricing-card` |
| Casos de clientes | `<section ... id="depoimentos">` → `.testi-card` |
| Campos do formulário | `<form class="lead-form" id="lead-form">` |
| Mensagem enviada ao WhatsApp | `<script>` → variável `whatsappMessage` |

> 💡 Dica: todo o texto visível está em português — não há ficheiros de tradução/i18n. Se precisares de uma versão noutro idioma, terás de duplicar o ficheiro.

---

## 💬 Integração com WhatsApp

Há **duas formas** de contacto via WhatsApp nesta página:

1. **Links directos** (`<a href="https://wa.me/244933609090?text=...">`) — no botão flutuante e no CTA final. O texto já vem preenchido via `encodeURIComponent` na própria URL.
2. **Formulário → WhatsApp** — o formulário `#lead-form` **não envia dados para nenhum servidor**. O JavaScript:
   - Captura os campos (`FormData`)
   - Monta uma mensagem de texto formatada
   - Abre uma nova aba com `wa.me/<numero>?text=<mensagem>`

Isto significa que **não há armazenamento de leads** — cada submissão depende do utilizador enviar manualmente a mensagem já aberta no WhatsApp. Se precisares de guardar os leads (ex: numa base de dados ou Firebase), é necessário adicionar essa lógica.

---

## 📱 Responsividade

Dois breakpoints principais:

```css
@media (max-width: 900px) {
  /* hero empilha em coluna única, mockup de dashboard escondido */
  /* features grid passa de 3 para 2 colunas */
  /* pricing e testimonials passam para 1 coluna */
  /* nav-links escondidos (sem menu hambúrguer implementado) */
}
@media (max-width: 600px) {
  /* features grid passa para 1 coluna */
  /* formulário empilha campos em linha única */
}
```

⚠️ **Nota importante:** os `.nav-links` desaparecem em ecrãs ≤900px e **não há menu hambúrguer** para os substituir. Em mobile, a navegação fica apenas com o logo e o botão "Pedir Orçamento". Isto é uma limitação a resolver se o tráfego mobile for relevante (ver [Próximos passos](#-próximos-passos-sugeridos)).

---

## 🎬 Animações e interações

| Efeito | Mecanismo |
|---|---|
| Fade-up ao entrar na viewport | `IntersectionObserver` + classe `.fade-up` / `.visible` |
| Navbar muda cor da borda ao fazer scroll | listener de `scroll` no `<nav>` |
| Parallax suave em orbs e mockups | listener de `scroll` com `requestAnimationFrame`, respeita `prefers-reduced-motion` |
| Flutuação do dashboard mockup | `@keyframes float` (CSS puro) |
| Pulsar do badge do hero | `@keyframes pulse` |
| Marquee dos clientes/stack | `@keyframes marquee`, loop infinito via duplicação de itens no HTML |
| Hover em cartões | `transform: translateY(-4px)` + mudança de borda |

Todas as animações JS respeitam `window.matchMedia('(prefers-reduced-motion: reduce)')` — utilizadores com essa preferência não terão o efeito parallax.

---

## 🚀 Deploy

### Vercel
```bash
# instalar CLI (uma vez)
npm i -g vercel

# a partir da pasta onde está o index.html
vercel --prod
```
Ou arrasta a pasta directamente para [vercel.com/new](https://vercel.com/new).

### Netlify
Arrasta a pasta (ou apenas o `index.html`) para [app.netlify.com/drop](https://app.netlify.com/drop).

### Namecheap / hosting tradicional
Faz upload do `index.html` via FTP/cPanel para a pasta `public_html`.

Não é necessário nenhum passo de build — o ficheiro já está pronto para produção tal como está.

---

## ✅ Checklist antes de publicar

- [ ] Confirmar/actualizar os **preços** dos 3 pacotes (são valores de referência)
- [ ] Confirmar se o número de WhatsApp `+244 933 609 090` está correcto em todos os locais
- [ ] Rever os **casos de clientes** — confirmar se Grande Seba, A.M.P. e Barber Shop Panguila autorizam ser citados publicamente
- [ ] Adicionar meta tags de SEO (`description`, `og:title`, `og:image`, favicon) — actualmente ausentes
- [ ] Testar o formulário em telemóvel real (o link `wa.me` comporta-se de forma diferente em iOS/Android/desktop)
- [ ] Verificar todos os links do rodapé (`Termos`, `Privacidade`, `Suporte` apontam para `#`)
- [ ] Testar em pelo menos 2 tamanhos de ecrã móvel (não há menu mobile)

---

## ⚠️ Placeholders que precisam de dados reais

| Local | Valor actual | Acção recomendada |
|---|---|---|
| Preço "Site Institucional" | 80.000 Kz | Substituir pelo preço real praticado |
| Preço "Loja Online / Sistema Web" | 180.000 Kz | Substituir pelo preço real praticado |
| Estatística "10 projectos entregues" | Contagem aproximada dos projectos conhecidos | Ajustar ao número exacto real |
| Estatística "6 sectores atendidos" | Estimativa (retalho, hotelaria, governo, agricultura, educação, transportes) | Confirmar/ajustar |
| Meta description / Open Graph | Inexistente | Adicionar para partilha em redes sociais |
| Favicon | Inexistente | Adicionar `<link rel="icon" ...>` |
| Links `Termos`, `Privacidade`, `Suporte` | `href="#"` | Criar páginas reais ou remover do footer |

---

## ♿ Acessibilidade

Pontos já cobertos:
- `prefers-reduced-motion` respeitado no parallax
- Contraste alto (fundo escuro + texto branco) na maior parte do conteúdo
- Estrutura semântica (`<nav>`, `<section>`, `<footer>`, `<form>`)

Pontos a melhorar:
- Faltam atributos `alt` (não há `<img>`, mas os SVGs decorativos podem beneficiar de `aria-hidden="true"`)
- O botão flutuante do WhatsApp tem `title`, mas beneficiaria de `aria-label`
- Não há indicação visível de foco de teclado customizada (depende do estilo padrão do browser)
- Falta um "skip to content" para utilizadores de leitor de ecrã

---

## 🌐 Compatibilidade de navegadores

Testado visualmente para:
- Chrome / Edge (Chromium) — recomendado
- Firefox
- Safari (desktop e iOS)

Recursos usados que exigem browsers modernos: `backdrop-filter` (blur da navbar), CSS custom properties, `IntersectionObserver`, `grid`. Não há polyfills — browsers muito antigos (IE11) não são suportados.

---

## 🕓 Histórico de alterações

**[Actual] Reconversão de restaurante → agência**
- Removido todo o conteúdo específico de gestão de restaurantes (PDV, mesas, QR de menu, pedidos de cozinha)
- Hero, dashboard mockup, features, processo, preços, depoimentos e formulário reescritos para reflectir os serviços reais da Nexora Systems
- Adicionada nova faixa de stack tecnológica (marquee)
- Faixa de clientes actualizada com nomes reais de projectos entregues

**[Anterior] Versão original**
- Landing page de produto SaaS "Nexora Systems" para gestão de restaurantes (PDV, mesas com QR code, gestão de estoque, relatórios de vendas)

---

## 🔮 Próximos passos sugeridos

1. **Menu mobile (hambúrguer)** — actualmente os links de navegação desaparecem sem substituto em ecrãs pequenos
2. **Captação real de leads** — ligar o formulário a um backend leve (ex: Firebase Firestore, como já usas noutros projectos) para não depender só do envio manual via WhatsApp
3. **SEO básico** — meta description, Open Graph, favicon, `sitemap.xml`
4. **Página de casos de estudo** — cada cliente (Grande Seba, Canto da Engenharia, A.M.P., etc.) poderia ter uma página própria com mais detalhe e screenshots
5. **Depoimentos reais** — substituir as descrições factuais por citações directas dos clientes, com autorização
6. **Analytics** — adicionar Google Analytics ou Plausible para medir conversões do formulário e do botão de WhatsApp

---

*Documento gerado como parte da reconversão da landing page da Nexora Systems (2026).*
