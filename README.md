<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=30&duration=4000&pause=1000&color=FB2C36&center=true&vCenter=true&random=false&width=650&lines=Guilherme+Oliveira;Full+Stack+Developer;Angular+%7C+React+%7C+.NET+%7C+Spring+Boot" alt="Typing SVG" />

<br/>

**Construo produtos inteiros — do banco de dados ao pixel.**

<br/>

[![Portfolio](https://img.shields.io/badge/Portfolio-FB2C36?style=for-the-badge&logo=vercel&logoColor=white)](https://guikbit.vercel.app)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/guilherme-oliveira-771318203/)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:guilhermeoliveira1998@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/GuikBit)

</div>

---

## Sobre mim

Desenvolvedor **Full Stack** com experiência sólida nas duas pontas: as interfaces que as pessoas usam todo dia e as arquiteturas que as sustentam. Meu trabalho recente é um **SaaS multi-tenant em produção** — não um exercício: tem clientes reais, dinheiro passando por dentro e uptime que importa.

- **Atuação:** Full Stack Developer na [Pluri Sistemas](https://github.com/GuikBit)
- **Localização:** Juiz de Fora, MG — Brasil
- **Foco atual:** React 19, Next.js, Spring Boot, .NET e arquiteturas multi-tenant
- **Especialidades:** APIs RESTful, integrações de pagamento, automação com IA, design systems

> *"Clean code, great design, powerful solutions."*

---

## Projeto em destaque — Bellory

**SaaS multi-tenant de gestão para barbearias, salões de beleza e clínicas de estética.** Um único produto que cobre o caminho inteiro, da captação do cliente ao fechamento do caixa: site de vendas, agendamento online, painel administrativo completo, e-commerce, financeiro, pagamento online e um agente de IA que atende pelo WhatsApp.

<div align="center">

[![Site](https://img.shields.io/badge/bellory.com.br-FB2C36?style=for-the-badge&logo=googlechrome&logoColor=white)](https://bellory.com.br)
[![App](https://img.shields.io/badge/app.bellory.com.br-1E3C64?style=for-the-badge&logo=react&logoColor=white)](https://app.bellory.com.br)

</div>

### Arquitetura

```mermaid
flowchart LR
    A["Site + BellLink<br/>Next.js 16"] --> API
    B["Painel do salão<br/>React 19 · PWA"] --> API
    C["Super Admin<br/>React + Vite"] --> ADM["Bellory-Admin-API<br/>Spring Boot"]
    API["<b>Bellory-API</b><br/>Spring Boot 3.3 · Java 21"] --> DB[("PostgreSQL<br/>113 migrations")]
    API --> RD[("Redis<br/>cache de assinatura")]
    API --> MP{{"Mercado Pago<br/>Pro + Transparente"}}
    API --> WA{{"WhatsApp<br/>Evolution API + n8n"}}
```

### Os módulos

<table>
<tr>
<td width="50%" valign="top">

#### [Bellory-API](https://github.com/GuikBit/Bellory-API) — o núcleo
**Java 21 · Spring Boot 3.3 · PostgreSQL · Redis**

O cérebro do produto, e onde vive toda regra de negócio. Multi-tenancy por contexto de requisição, RBAC com 7 papéis e 60+ permissões granulares, e um domínio financeiro de verdade — contas a pagar e receber, DRE, fluxo de caixa, comissionamento e conciliação de cobranças.

Integra **Mercado Pago nos dois modos** (Checkout Pro e Transparente/Orders API), com o webhook como fonte da verdade do pagamento; dispara **WhatsApp** por Evolution API + fluxos n8n; emite relatórios em CSV, PDF e XLSX; e envia **Web Push** (VAPID).

`Spring Security + JWT` · `Flyway` · `JPA/Hibernate` · `OpenAPI` · `Caffeine + Redis` · `OpenPDF` · `Apache POI`

</td>
<td width="50%" valign="top">

#### [Bellory-front](https://github.com/GuikBit/barbearia) — o painel do salão
**React 19 · TypeScript · Vite 8 · PWA**

O sistema que o dono do salão abre todo dia: agenda multiprofissional, clientes, colaboradores, serviços, pacotes de crédito pré-pago, estoque com Kardex auditável, PDV, financeiro e relatórios.

É um **PWA de verdade** — o Service Worker enfileira mutações com Background Sync, então a agenda continua funcionando sem internet e sincroniza sozinha quando ela volta. Cada tenant escolhe entre **6 temas**, com cores e tipografia vindas da API e aplicadas em tempo de execução.

`TanStack Query` · `PrimeReact` · `Tailwind v4` · `Framer Motion` · `Chart.js` · `Three.js` · `vite-plugin-pwa`

</td>
</tr>
<tr>
<td width="50%" valign="top">

#### [Bellory](https://github.com/GuikBit/Bellory) — site
**Next.js 16 · App Router · TypeScript**

A vitrine e a porta de entrada. Site de marketing com páginas por segmento, SEO estruturado em JSON-LD e CSS crítico inlined no build para Core Web Vitals.

Hospeda também o **BellLink**, o "link na bio" de cada salão: página pública com vitrine de produtos, horários e um **fluxo de agendamento completo embutido** — identificação por telefone, escolha de serviço e profissional, cupom de desconto e pagamento com Payment Brick, sem sair da página.

`Server Components` · `ISR` · `React Query` · `Framer Motion` · `Zod` · `Leaflet`

</td>
<td width="50%" valign="top">

#### [Bellory-admin](https://github.com/GuikBit/Bellory-admin) + [Admin-API](https://github.com/GuikBit/Bellory-Admin-API)
**React · Spring Boot · Docker**

O painel de quem opera a plataforma, não o salão: gestão de tenants, planos e assinaturas, blocklist de slugs reservados e visão consolidada da base.

<br/>

#### [Bellory-docs](https://github.com/GuikBit/Bellory-docs)
**Markdown · n8n**

Cerca de 90 especificações técnicas versionadas e os fluxos reais do **agente de IA** que consulta horários, agenda, reagenda e cadastra clientes pelo WhatsApp.

</td>
</tr>
</table>

### Engenharia em números

<div align="center">

| Módulo | Escala | Stack |
|:---|:---|:---|
| **Bellory-API** | 485 endpoints · 875 classes · 142 entidades · 113 migrations | Java 21 · Spring Boot 3.3 |
| **Painel do salão** | 456 arquivos · ~182k linhas · 206 componentes | React 19 · Vite 8 · TS |
| **Site + BellLink** | 199 arquivos · SSG + ISR | Next.js 16 · React 19 |
| **Ecossistema** | **5 repositórios** · **+1.300 commits** | Full Stack |

</div>

---

## Payment API — infraestrutura de pagamentos multi-tenant

**Gateway de cobranças como serviço, integrado ao Asaas.** Uma API que várias aplicações consomem para cobrar: clientes, planos, assinaturas recorrentes, cobranças em PIX, boleto e cartão, webhooks e troca de plano com cálculo pró-rata. É o serviço que a própria Bellory usa para gerir assinaturas.

O diferencial não é o CRUD — é o que sustenta dinheiro em produção: **isolamento de tenant no próprio banco (PostgreSQL Row-Level Security)**, chaves de idempotência em toda escrita, circuit breaker e retry no gateway externo, segredos cifrados em repouso e observabilidade de ponta a ponta.

<table>
<tr>
<td width="50%" valign="top">

#### [Paymant-API](https://github.com/GuikBit/Paymant-API) — o serviço
**Java 21 · Spring Boot 3.4 · PostgreSQL 16 · Redis 7**

Multi-tenancy por **RLS**: a separação é imposta pelo banco, não por um `where` que alguém pode esquecer. Integração com o Asaas protegida por **Resilience4j** (circuit breaker, retry e rate limiter), webhooks idempotentes e reconciliação de cobranças.

Observabilidade completa — **Micrometer + Prometheus + OpenTelemetry**, dashboard de Grafana e alertas versionados no repo. Testes com **TestContainers**, **WireMock** e **jqwik** (property-based), mais **k6** para carga: criação de cobrança, flood de webhook e relatórios.

`Spring Security + JWT` · `Flyway` · `MapStruct` · `Jasypt` · `Docker Compose` · `OpenAPI`

</td>
<td width="50%" valign="top">

#### [Payment-API---WEB](https://github.com/GuikBit/Payment-API---WEB) — o console
**React 19 · Vite 8 · TypeScript · Tailwind 4**

SPA dark-first para operar e testar a API: cobranças, assinaturas, trocas de plano, webhooks, reconciliação e relatórios.

O cliente HTTP resolve sozinho o que costuma vazar para as telas — **refresh automático no 401**, header de tenant (`X-Company-Id`) e **chave de idempotência gerada em todo POST**. Estado servidor no TanStack Query, estado de sessão no Zustand, formulários com React Hook Form + Zod.

`Radix UI` · `TanStack Table` · `Recharts` · `Framer Motion` · `Zustand` · `Sonner`

</td>
</tr>
</table>

<div align="center">

| Módulo | Escala | Stack |
|:---|:---|:---|
| **Paymant-API** | 115 endpoints · 266 classes · 14 migrations · 27 suítes de teste | Java 21 · Spring Boot 3.4 |
| **Payment-API---WEB** | 139 arquivos TypeScript | React 19 · Vite 8 · Tailwind 4 |

</div>

---

<!-- ## Outros projetos

<table>
<tr>
<td width="50%" valign="top">

### OdontoSync — gestão odontológica
Sistema integrado para clínicas odontológicas: prontuário, agenda e faturamento, com aplicativo mobile para o paciente.

| Componente | Stack |
|:---|:---|
| **[Angular-Odonto](https://github.com/GuikBit/Angular-Odonto)** | Angular + PrimeNG |
| **[API-Odonto](https://github.com/GuikBit/API-Odonto)** | C# / .NET + MySQL |
| **[Mobile-Odonto](https://github.com/GuikBit/Mobile-Odonto)** | React Native + Expo |

</td>
<td width="50%" valign="top">

### [AgenteIA](https://github.com/GuikBit/AgenteIA) — agente inteligente
Experimentos com agentes de IA em TypeScript: RAG, tool calling e orquestração de conversas.

<br/>

### Todos os repositórios
Mais de 20 projetos entre APIs, front-ends e experimentos.

[![Repos](https://img.shields.io/badge/Ver_todos-FB2C36?style=flat-square&logo=github&logoColor=white)](https://github.com/GuikBit?tab=repositories)

</td>
</tr>
</table>

--- -->

## Stack tecnológico

<div align="center">

#### Linguagens
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Java](https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=openjdk&logoColor=white)
![C#](https://img.shields.io/badge/C%23-512BD4?style=for-the-badge&logo=csharp&logoColor=white)

#### Frontend
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![React Native](https://img.shields.io/badge/React_Native-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![PrimeReact](https://img.shields.io/badge/PrimeReact-DD0031?style=for-the-badge&logo=react&logoColor=white)

#### Backend
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white)

#### Dados e infraestrutura
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Flyway](https://img.shields.io/badge/Flyway-CC0200?style=for-the-badge&logo=flyway&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

#### Integrações e ferramentas
![Mercado Pago](https://img.shields.io/badge/Mercado_Pago-00B1EA?style=for-the-badge&logo=mercadopago&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)
![OpenAPI](https://img.shields.io/badge/OpenAPI-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![k6](https://img.shields.io/badge/k6-7D64FF?style=for-the-badge&logo=k6&logoColor=white)

</div>

---

## Métricas de contribuição

<div align="center">

<img width="98%" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=guikbit&theme=tokyo_night" alt="Resumo do perfil" />

<img width="49%" src="https://streak-stats.demolab.com?user=guikbit&theme=tokyonight&hide_border=true&background=0D1117&stroke=FB2C36&ring=FB2C36&fire=FB2C36&currStreakLabel=FB2C36" alt="Sequência de contribuições" />
<img width="49%" src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=guikbit&theme=tokyo_night" alt="Estatísticas gerais" />

<img width="49%" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=guikbit&theme=tokyo_night" alt="Commits por linguagem" />
<img width="49%" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=guikbit&theme=tokyo_night" alt="Repositórios por linguagem" />

<img width="60%" src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=guikbit&theme=tokyo_night&utcOffset=-3" alt="Horários mais produtivos" />

</div>

---

<!--
  Trofeus e snake removidos: os dois provedores (github-profile-trophy.vercel.app e a
  branch `output` deste repo) nao estavam renderizando.

  Para ligar o snake: copie `snake-workflow.yml` para .github/workflows/ neste repositorio
  (GuikBit/GuikBit), rode a Action uma vez e descomente a linha abaixo.

<div align="center">

![Snake animation](https://raw.githubusercontent.com/GuikBit/GuikBit/output/github-contribution-grid-snake-dark.svg)

</div>
-->

<div align="center">

```typescript
const developer = {
  name: "Guilherme Oliveira",
  role: "Full Stack Developer",
  stack: {
    frontend: ["React", "Next.js", "Angular", "React Native"],
    backend: ["Spring Boot", ".NET", "Node.js"],
    data: ["PostgreSQL", "MySQL", "MongoDB", "Redis"],
  },
  shipping: "Bellory — SaaS multi-tenant em produção",
  motto: "Clean code, great design, powerful solutions",
};
```

<br/>

**Aberto a novos desafios e oportunidades de colaboração.**

[![Portfolio](https://img.shields.io/badge/Visite_meu_portfólio-FB2C36?style=for-the-badge&logo=vercel&logoColor=white)](https://guikbit.vercel.app)

<br/>

![Profile Views](https://komarev.com/ghpvc/?username=guikbit&color=FB2C36&style=flat-square)

</div>
