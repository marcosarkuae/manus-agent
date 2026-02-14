# Project Context — Marcos Portes (ARK Group)

> Arquivo de contexto persistente para sessões de IA. Atualizado ao final de cada sessão relevante.
> Última atualização: 14 de Fevereiro de 2026

## Sobre
Este documento consolida o histórico de todas as tarefas e projetos executados, servindo como memória persistente entre sessões. No início de cada nova sessão, o agente deve ler este arquivo para carregar o contexto completo.

## Ecossistema de Projetos
- **ARK Group** — Holding de negócios (ARK Strategy, ARK Financial, ARK Technology, ARK Commercial, ARK Makers)
- **ARK Control Panel** — Plataforma web de geração de documentos com Multi-IA colaborativa (repo: ark-control-hub-v2)
- **ARK Hub** — Landing page centralizada para projetos pessoais
- **Portes Family Dashboard** — Dashboard familiar com metas 2026 e sistema de check-in
- **Marcos Personal Dashboard** — Dashboard pessoal com 45 metas quantificáveis
- **Zion Capital** — Reestruturação de dívida
- **ARK Financial** — Advisory de investimentos em criptoativos (Cliente: José Blesa)

## Informações do Usuário
- **Nome:** Marcos Paulo Rezende Portes
- **Localização:** Dubai, UAE (GMT+4)
- **Email profissional:** marcos@arkstrategy.ae
- **Email pessoal:** marcos.arkuae@gmail.com
- **WhatsApp:** +971 52 362 0109
- **Perfil:** Técnico/matemático, respostas diretas e resolutivas
- **Família:** Luana (esposa), Lucca (16 anos, futebol Sub-16), Davi (11 anos, futebol Sub-12)

---

## Índice

1. [Dashboard Família Portes (Metas 2026 + Check-in)](#1-dashboard-família-portes--metas-2026-e-sistema-de-check-in)
2. [ARK Control Panel (Plataforma Multi-IA)](#2-ark-control-panel--plataforma-de-geração-de-documentos-com-multi-ia-colaborativa)
3. [Expansão Metas 2026 + Pesquisa Educacional Dubai](#3-expansão-do-sistema-de-metas-2026--pesquisa-educacional-dubai)
4. [Plano de Investimento Criptoativos (ARK Financial / José Blesa)](#4-criação-de-plano-de-investimento-em-criptoativos--ark-financial-cliente-josé-blesa)
5. [Apresentações Imobiliárias Premium + Análise Legal](#5-criação-de-apresentações-imobiliárias-premium-para-clientes-eau--análise-legal-de-pagamento-internacional)
6. [Holding Internacional Fabio Celestini](#6-estruturação-fiscal-e-patrimonial-de-holding-internacional-para-fabio-celestini)
7. [Framework Contratual ARK Group v2.0](#7-framework-contratual-ark-group-v20-com-design-system-corporativo)
8. [Google Workspace ARK Strategy](#8-configuração-completa-de-email-profissional-e-google-workspace-para-arkstrategyae)
9. [Currículos Esportivos (Lucca e Davi)](#9-criação-de-currículos-esportivos-lucca-e-davi--slides-e-pdfs)
10. [Landing Page Ark Hub](#10-criação-de-landing-page-ark-hub--central-de-projetos-pessoais)
11. [Reestruturação de Dívida (Zion Capital)](#11-reestruturação-de-acordo-de-dívida-com-cenários-mutuamente-excludentes-e-proteção-standstill-progressivo)

---

## 1. Dashboard Família Portes — Metas 2026 e Sistema de Check-in

**Data:** 12-14 de Janeiro de 2026  
**Status:** Concluída  
**Projeto relacionado:** Dashboard Família Portes (portes_family_dashboard)

---

### O que foi feito

#### 1. Atualização Completa de Metas 2026
- **Deletadas todas as metas antigas** do banco de dados
- **Criadas 62 novas metas de 2026** distribuídas entre 4 membros:
  - **Marcos Portes:** 18 metas (386.500 AED)
  - **Luana Portes:** 18 metas (14.530 AED)
  - **Davi Victorio:** 12 metas (3.300 AED)
  - **Lucca Victorio:** 14 metas (8.000 AED)
- **Valor total:** 412.330 AED em investimentos

#### 2. Sistema de Imagens de Produtos
- **Adicionado campo `imageUrl` e `productLink`** na tabela `goals` do schema (`drizzle/schema.ts`)
- **Migração aplicada** via `pnpm db:push`
- **Imagens copiadas** para `/home/ubuntu/portes_family_dashboard/client/public/products/`:
  
  **Marcos Portes:**
  - `rolex-yacht-master.jpeg` - Rolex Yacht-Master Rose Gold (150.000 AED)
  - `omega-snoopy.jpeg` - Omega Speedmaster Snoopy 50th (50.000 AED)
  - `lv-sneakers.jpeg` - Tênis Louis Vuitton All Black (3.000 AED)
  
  **Luana Portes:**
  - `ysl-bag.jpeg` - Bolsa YSL Loulou Micro (3.950 AED)
  - `hermes-sandal.jpeg` - Papete Hermès Chypre (4.490 AED)
  - `rimowa-pink.jpeg` - Mala Rimowa Ballerina (6.090 AED)
  - `ysl-phone-holder.jpeg` - Cassandre Phone Holder YSL (3.050 AED)
  
  **Davi Victorio:**
  - `ps5-controller.jpeg` - Controle PS5 Fortnite Edition (300 AED)
  - `santos-jersey.jpeg` - Camisa Santos

- **Interface atualizada** em `client/src/pages/MemberProfile.tsx` para exibir miniaturas 64x64px e links "🔗 Ver produto"

#### 3. Sistema de Filtros por Tipo de Meta
- **Implementado em `MemberProfile.tsx`** com 4 filtros:
  - **Todas** - Exibe todas as metas
  - **Com Valor** - Apenas metas com `valueAED > 0` (ícone $)
  - **Sem Valor** - Metas qualitativas com `valueAED = 0` (ícone 🎯)
  - **Jejuns/Propósitos** - Metas com `notes` contendo "Jejum 2026" ou "Propósito 2026" (ícone ❤️)
- **Contadores dinâmicos** em cada botão de filtro
- **Estado local** gerenciado via `useState` com filtragem em tempo real

#### 4. Seção de Jejuns e Propósitos 2026
- **Card destacado** adicionado no topo dos perfis (após header do membro)
- **Estilo:** Background gradiente roxo/rosa (`bg-gradient-to-br from-purple-50 to-pink-50`)
- **Exibe todos os jejuns e propósitos** do membro com ícone de coração
- **Integrado** com sistema de check-in (botões visíveis diretamente no card)

#### 5. Sistema de Check-in Diário
- **Tabela `goalCheckIns` criada** em `drizzle/schema.ts`:
  ```typescript
  export const goalCheckIns = sqliteTable("goal_check_ins", {
    id: integer("id").primaryKey({ autoIncrement: true }),
    goalId: integer("goal_id").notNull().references(() => goals.id, { onDelete: "cascade" }),
    date: text("date").notNull(), // Formato: "YYYY-MM-DD"
    completed: integer("completed", { mode: "boolean" }).notNull().default(true),
    notes: text("notes"),
    createdAt: integer("created_at", { mode: "timestamp" }).notNull().default(sql`(unixepoch())`),
  });
  ```

- **Procedures tRPC criadas** em `server/routers.ts`:
  - `goalCheckIn.create` - Registra check-in diário
  - `goalCheckIn.getByGoal` - Consulta check-ins por meta
  - `goalCheckIn.getStats` - Calcula estatísticas (total de dias, streak consecutivo)

- **Funções no banco** em `server/db.ts`:
  - `createCheckIn(goalId, date, completed, notes)` - Insere check-in
  - `getCheckInsByGoal(goalId)` - Retorna todos os check-ins de uma meta
  - `getCheckInStats(goalId)` - Calcula total de dias e streak

- **Componente `CheckInButton.tsx` criado**:
  - Botão azul "Check-in" quando não feito hoje
  - Botão verde "✓ Feito hoje!" quando já registrado
  - Exibe contador "X dias" e streak "🔥 Y" abaixo do botão
  - Usa `trpc.goalCheckIn.create.useMutation()` para registrar
  - Usa `trpc.goalCheckIn.getStats.useQuery()` para estatísticas

#### 6. Alteração de Jejuns do Marcos
- **Removido:** Jejum de Chocolate
- **Adicionados:**
  - Jejum de Pink Barry - "Não comer Pink Barry o ano todo"
  - Jejum de Clash Royale - "Não jogar Clash Royale o ano todo"

#### 7. Diferenciação entre Jejuns e Propósitos
- **Conceitos clarificados:**
  - **JEJUNS** = Proibições absolutas (coisas que NÃO PODE de jeito nenhum)
  - **PROPÓSITOS** = Metas/compromissos (coisas que VAI fazer)

- **Metas atualizadas:**
  - "Jejum de Açaí/Pink Berry/Refri" → "Propósito: Açaí/Pink Berry/Refri apenas finais de semana"
  - "Jejum de Acordar Tarde" → "Propósito: Não acordar depois das 10h"
  - Campo `notes` alterado de "Jejum 2026" para "Propósito 2026"

- **Estrutura final do Marcos:**
  - **Jejuns (2):** Pink Barry, Clash Royale
  - **Propósitos (2):** Açaí/Refri finais de semana, Acordar antes das 10h

### Decisões técnicas relevantes

#### Schema e Banco de Dados
- **Campo `date` como `text`** na tabela `goalCheckIns` (formato "YYYY-MM-DD") ao invés de timestamp para facilitar queries por dia
- **Campo `categoryId` obrigatório** na tabela `goals` (sem default) - todas as metas precisam de categoria
- **Cascade delete** configurado em `goalCheckIns.goalId` para deletar check-ins automaticamente quando meta é deletada
- **Campo `notes`** usado para diferenciar "Jejum 2026" vs "Propósito 2026" ao invés de criar campo booleano separado

#### Frontend
- **Filtros implementados com estado local** (`useState`) ao invés de query parameters para evitar reload de página
- **Miniaturas de produtos em 64x64px** com `object-contain` para evitar distorção
- **Componente CheckInButton reutilizável** que encapsula lógica de check-in e exibição de estatísticas
- **Seção de Jejuns/Propósitos como card separado** ao invés de misturar com lista de metas por categoria

#### tRPC e Backend
- **Procedures separados** para check-in (create, getByGoal, getStats) ao invés de um único endpoint genérico
- **Cálculo de streak no backend** via SQL com `GROUP BY` e `HAVING` para performance
- **Superjson habilitado** permite retornar objetos Date diretamente sem serialização manual

### Pendências e próximos passos

#### Melhorias Sugeridas
1. **Calendário Visual de Check-ins**
   - Modal com calendário mensal mostrando dias cumpridos (verde) e falhados (cinza)
   - Permite visualizar padrões e histórico completo de cada jejum/propósito

2. **Notificações de Lembrete**
   - Sistema de notificações diárias (push ou email) lembrando check-in
   - Horário personalizável por usuário

3. **Página de Ranking Familiar**
   - Comparação de progresso entre membros
   - Quem tem maior streak, taxa de cumprimento
   - Estatísticas gerais para gamificar acompanhamento

4. **Separação Visual Jejuns vs Propósitos**
   - Duas seções distintas: "🚫 Jejuns 2026" (vermelho) e "🎯 Propósitos 2026" (verde)
   - Ícones personalizados (🚫 para jejuns, 🎯 para propósitos)

5. **Relatório Mensal Comparativo**
   - Gerar relatório automático comparando taxa de sucesso
   - Jejuns: 0 falhas = 100%
   - Propósitos: dias cumpridos/total
   - Enviado todo dia 1º do mês

#### Bugs Conhecidos
- **Erro de import no CheckInButton.tsx:** Tentativa de importar `@/hooks/use-toast` que não existe
  - **Solução aplicada:** Removido toast e usado `alert()` simples
  - **Melhoria futura:** Implementar sistema de toast global

#### Histórico de Check-ins
- **Não implementado:** Modal/dialog com calendário de histórico mensal
- **Motivo:** Priorizado funcionalidade básica de check-in diário
- **Próximo passo:** Criar componente `CheckInHistory.tsx` com calendário interativo

### Arquivos e artefatos

#### Arquivos Modificados

**Schema e Banco de Dados:**
- `drizzle/schema.ts` - Adicionados campos `imageUrl`, `productLink` em `goals` e tabela `goalCheckIns`
- `server/db.ts` - Funções `createCheckIn`, `getCheckInsByGoal`, `getCheckInStats`
- `server/routers.ts` - Router `goalCheckIn` com procedures `create`, `getByGoal`, `getStats`

**Frontend:**
- `client/src/pages/MemberProfile.tsx` - Seção de jejuns/propósitos, filtros, exibição de imagens
- `client/src/components/CheckInButton.tsx` - Componente de check-in (NOVO)
- `client/public/products/` - Diretório com 9 imagens de produtos (NOVO)

**Documentação:**
- `todo.md` - Histórico de tarefas concluídas
- `imagens_produtos_encontradas.md` - Mapeamento de imagens para produtos
- `testes_melhorias_finais.md` - Resultados dos testes de filtros e check-in
- `sistema_checkin_testes.md` - Documentação de testes do sistema de check-in

#### Checkpoints Criados

1. **Version: b36c347d** - "Metas 2026 atualizadas com imagens de produtos"
   - 62 metas criadas
   - 3 imagens do Marcos adicionadas
   - Total: 412.330 AED

2. **Version: 29c63262** - "3 melhorias finais implementadas"
   - Imagens da Luana e Davi
   - Seção de jejuns/propósitos
   - Sistema de filtros

3. **Version: 71d93d53** - "Sistema de check-in implementado"
   - Tabela goalCheckIns
   - Procedures tRPC
   - Componente CheckInButton
   - 4 imagens da Luana

4. **Version: cf576b14** - "Alteração de Jejuns do Marcos para 2026"
   - Removido Jejum de Chocolate
   - Adicionados Jejum de Pink Barry e Clash Royale

5. **Version: 2b6a013d** - "Diferenciação entre Jejuns e Propósitos"
   - Conceitos clarificados
   - Títulos atualizados com prefixo "Propósito:"
   - Notes alterados para "Propósito 2026"

#### URLs e Deploy
- **Dev Server:** https://3000-i496qjvxon4x7lobm9hqh-efed44ae.sg1.manus.computer
- **Projeto Manus:** Portes Family (Vg5MNFDfPASJaQBXj97Ssv)
- **Path local:** /home/ubuntu/portes_family_dashboard
- **Features:** db, server, user

#### Imagens de Produtos (Assets)
```
client/public/products/
├── rolex-yacht-master.jpeg (Marcos - 150k AED)
├── omega-snoopy.jpeg (Marcos - 50k AED)
├── lv-sneakers.jpeg (Marcos - 3k AED)
├── ysl-bag.jpeg (Luana - 3.95k AED)
├── hermes-sandal.jpeg (Luana - 4.49k AED)
├── rimowa-pink.jpeg (Luana - 6.09k AED)
├── ysl-phone-holder.jpeg (Luana - 3.05k AED)
├── ps5-controller.jpeg (Davi - 300 AED)
└── santos-jersey.jpeg (Davi)
```

#### Estatísticas Finais

- **Total de metas:** 66 (62 novas + 4 antigas não deletadas)
- **Valor total:** 412.330 AED
- **Membros:** 4 (Marcos, Luana, Davi, Lucca)
- **Jejuns/Propósitos do Marcos:** 4 (2 jejuns + 2 propósitos)
- **Produtos com imagem:** 9 (3 Marcos + 4 Luana + 2 Davi)
- **Checkpoints criados:** 5
- **Arquivos modificados:** 8
- **Componentes novos:** 1 (CheckInButton.tsx)
- **Tabelas criadas:** 1 (goalCheckIns)

#### Resumo Técnico para Continuação

**Stack:**
- React 19 + Tailwind 4 + Express 4 + tRPC 11
- Drizzle ORM + SQLite (TiDB em produção)
- Superjson para serialização
- Manus OAuth para autenticação

**Padrões de Código:**
- Procedures tRPC em `server/routers.ts`
- Query helpers em `server/db.ts`
- Componentes de página em `client/src/pages/`
- Componentes reutilizáveis em `client/src/components/`
- Assets estáticos em `client/public/`

**Comandos Úteis:**
```bash
pnpm db:push          # Aplicar mudanças no schema
pnpm dev              # Iniciar dev server
pnpm test             # Rodar testes vitest
```

**Próxima Sessão:**
- Implementar calendário visual de check-ins
- Separar visualmente jejuns de propósitos
- Criar página de ranking familiar

---

## 2. ARK Control Panel — Plataforma de Geração de Documentos com Multi-IA Colaborativa

**Data:** 07 de janeiro a 14 de fevereiro de 2026  
**Status:** Em andamento  
**Projeto relacionado:** Ark Group (Lap5wRprqDR5x9DiXU3WBL) — ark-control-panel  
**Repositório GitHub:** Vinculado via Management UI (Settings → GitHub)  
**URL de Preview:** `https://3000-iy12xs4y7mr7zeb9a3bnz-01dd5e58.sg1.manus.computer`  
**Último Checkpoint:** `0195ab8b`

---

## O que foi feito

### 1. Arquitetura Core — Sistema Colaborativo de 4 IAs

Foi construída uma plataforma web completa que orquestra **4 modelos de IA** trabalhando em sequência colaborativa para gerar documentos de negócios robustos:

| IA | Modelo | Papel | Max Tokens | Ordem |
|---|---|---|---|---|
| **Gemini** | `gemini-2.0-flash` | Estrutura e Narrativa (1ª IA) | 8192 | 1 |
| **Manus** | API Manus (`api.manus.im`) | Estratégia e Visão de Negócios (2ª IA) | — | 2 |
| **OpenAI** | `gpt-4o` | Conteúdo Textual (3ª IA) | 16384 | 3 |
| **Claude** | Anthropic Claude | Revisão e Refinamento (4ª IA) | 8192 | 4 |

A consolidação final é feita em cascata com 4 estratégias de fallback:

1. **Estratégia 1:** OpenAI SDK com `AbortController` (timeout 60s)
2. **Estratégia 2:** Claude via `fetch()` nativo — bypass do SDK que ignora `AbortController` (bug #867 do `@anthropic-ai/sdk`)
3. **Estratégia 3:** Gemini com `Promise.race` (timeout 60s)
4. **Estratégia 4:** Fallback inteligente com scoring baseado em tamanho, tempo e qualidade estrutural

### 2. Três Modos de Operação

- **Modo Direto:** Consulta individual a uma ou mais IAs em paralelo (`Promise.allSettled`)
- **Modo Orquestrador:** GPT-4o analisa a tarefa, divide em subtarefas, atribui cada uma à IA mais adequada, executa em paralelo e consolida
- **Modo Colaborativo:** As 4 IAs trabalham em sequência (Gemini → Manus → OpenAI → Claude), cada uma contribuindo com sua especialidade, seguido de consolidação automática

### 3. Exportação de Documentos com Branding ARK Strategy

Implementados 4 formatos de exportação com identidade visual personalizada:

| Formato | Biblioteca | Branding |
|---|---|---|
| **PDF** | Custom `pdf-generator.ts` | Logo ARK Strategy, cores corporativas, cabeçalho/rodapé |
| **Word (DOCX)** | `docx-generator.ts` | Formatação profissional com estilos ARK |
| **PowerPoint (PPTX)** | `pptx-generator.ts` | Slides com layout ARK Strategy |
| **Nano Banana** | `manus-slides-generator.ts` | Integração com sistema de slides Manus |

### 4. Templates ARK Strategy (5 templates criados)

Criados e integrados ao banco de dados com API tRPC completa:

| Template | Slug | Categoria |
|---|---|---|
| Commission Statement (Extrato de Comissão) | `commission_statement` | financial |
| Consulting Agreement (Contrato de Consultoria) | `consulting_agreement` | contract |
| Partnership Agreement (Contrato de Parceria) | `partnership_agreement` | contract |
| Payment Receipt PREMIUM | `payment_receipt` | financial |
| Commercial Proposal PREMIUM | `commercial_proposal` | commercial |

Cada template possui variáveis dinâmicas (`{{VAR}}`), suporte multilíngue (ES/EN/PT) e especificações de design em JSON.

### 5. Interface de Geração de Documentos (`/documents`)

Página `DocumentGenerator.tsx` com:
- Seleção de templates da galeria
- Formulário dinâmico baseado nas variáveis do template selecionado
- Preview em tempo real do documento gerado
- Download em PDF/DOCX
- Histórico de documentos gerados

### 6. Sistema de Versionamento de Documentos Estratégicos

Estrutura em `/docs/strategic-plans/`:
- `VERSION_HISTORY.md` — changelog completo de todas as versões
- `CURRENT_VERSION.md` — ponteiro para a versão mais recente
- `v1.0_ROADMAP_2026-01-07.md` — documento original
- `v1.1_Strategic_Plan_2026-01-08.pdf` — versão com Learning Engine
- `v1.2_Strategic_Plan_2026-01-26.md` — análise de progresso (40-50% da Fase 1)
- `PROGRESS_ANALYSIS_v1.2.md` — análise detalhada de progresso vs roadmap

### 7. Dashboards e Monitoramento

| Rota | Componente | Função |
|---|---|---|
| `/dashboard` | `Dashboard.tsx` | Analytics gerais, médias de rating por IA |
| `/dashboards` | `Dashboards.tsx` | Hub de dashboards |
| `/dashboards/sessions` | `SessionsDashboard.tsx` | Histórico de sessões de colaboração |
| `/dashboards/api-monitoring` | `APIMonitoringDashboard.tsx` | Monitoramento de uso de APIs em tempo real |
| `/developer` | `DeveloperModePage.tsx` | Modo Desenvolvedor (análise de código pelas 4 IAs) |
| `/guests` | `GuestManagement.tsx` | Gerenciamento de convidados e permissões |
| `/notifications` | `NotificationSettings.tsx` | Configurações de notificações (email/WhatsApp) |

### 8. Funcionalidades Avançadas Implementadas

- **Cache de Respostas:** Tabela `responseCache` com hash MD5 do comando, evita chamadas duplicadas
- **Cache de Consolidações:** Tabela `consolidationCache` com hash SHA256 do conteúdo das 4 IAs
- **Sistema de Logs:** Tabela `logs` com níveis debug/info/warn/error e streaming em tempo real (`LogsPanel.tsx`)
- **Monitoramento de Custos:** Tabela `costs` com tokens input/output e custo estimado em USD por IA
- **Monitoramento de APIs:** Tabela `apiUsageLogs` com duração, tokens e status por operação
- **Bíblia ARK:** Upload de documentos de contexto (`documents` table) que são injetados automaticamente nos prompts das IAs
- **Sistema de Convites:** Tabela `accessInvites` com códigos únicos, limite de usos e expiração
- **Controle de Acesso por Role:** `guest`, `user`, `admin` com permissões granulares via `guestSettings`
- **Modo Iterativo:** Loop de melhoria contínua onde resultado de uma IA vira input da próxima iteração
- **Templates Dinâmicos:** Geração automática de templates baseados em orquestrações bem-sucedidas
- **Botão Cancelar (X vermelho):** Sempre visível durante execução, funciona independente do estado das IAs
- **Endpoint de Diagnóstico:** `/api/trpc/diagnostics.testApis` para testar todas as APIs e retornar status

### 9. Correções Críticas Resolvidas

| Bug | Causa Raiz | Solução |
|---|---|---|
| Gemini API falhando | API Key só suporta modelos 2.0/2.5, não `gemini-pro` ou `gemini-1.5-flash` | Trocado para `gemini-2.0-flash` |
| Claude travando 7+ minutos | `@anthropic-ai/sdk` ignora `AbortController` (bug #867) | Implementado `Promise.race` com `setTimeout` de 60s |
| Consolidação gerando 5 páginas | Prompt instruía "máximo 3000 caracteres" | Reescrito prompt com filosofia de liberdade criativa, removidos limites |
| Manus mostrando "Erro" quando desabilitada | Frontend não distinguia `SKIPPED_BY_USER` de erro real | Backend envia `error: 'SKIPPED_BY_USER'`, frontend exibe "Desabilitado" (badge amarelo) |
| Tela branca após exportar documento | Estados `isExecuting` e `startTime` não eram resetados | Adicionado reset de estado após `exportPDF`, `exportWord`, `exportPowerPoint` |
| OpenAI quota excedida (429) no Orquestrador | Uso intensivo esgotava quota | Sistema de fallback inteligente (Manus → Claude → OpenAI → Gemini) |

### 10. Simplificação de Templates (última melhoria)

Removidas seções pré-definidas dos templates das IAs. Agora os prompts dão **liberdade total** para cada IA criar sua própria estrutura, com meta de gerar **25-30+ seções** por IA e documentos finais de **80-100+ páginas**. Templates mantêm apenas: layout visual, tipografia e título.

---

## Decisões técnicas relevantes

### Stack e Arquitetura

- **Frontend:** React 19 + TypeScript + Tailwind CSS 4 + wouter (routing) + Recharts (gráficos)
- **Backend:** Express 4 + tRPC 11 + Drizzle ORM + MySQL/TiDB
- **Autenticação:** Manus OAuth com sessão via cookie JWT
- **Serialização:** SuperJSON (preserva `Date`, `BigInt`, etc. entre client/server)
- **Testes:** Vitest com 15+ testes unitários cobrindo templates, exportação, colaboração

### Decisões de Design

1. **`Promise.allSettled` em vez de `Promise.all`:** Garante que falha de uma IA não bloqueia as demais no modo direto.

2. **Claude via `fetch()` nativo em vez de SDK:** O `@anthropic-ai/sdk` tem bug conhecido (#867) que ignora `AbortController`. A solução foi usar `fetch()` direto com `stream: false` para que o timeout funcione.

3. **OpenAI como consolidador principal (16K tokens):** OpenAI GPT-4o suporta 16384 tokens de output (dobro do Claude com 8192), tornando-a ideal para consolidar documentos longos.

4. **Ordem Gemini → Manus → OpenAI → Claude:** Baseada nas forças reais de cada IA — Gemini é rápido para estrutura, Manus tem visão estratégica, OpenAI é criativo com alto output, Claude refina narrativa.

5. **4 estratégias de consolidação em cascata:** Garante que o sistema **nunca trava** — se uma estratégia falha, a próxima assume automaticamente.

6. **Prompts com liberdade criativa:** Removidas instruções limitantes ("gere exatamente X seções"). IAs agora têm liberdade total para definir estrutura, quantidade de seções e profundidade do conteúdo.

7. **Banco de dados como fonte de contexto:** Documentos da "Bíblia ARK" são armazenados no banco e injetados automaticamente nos prompts, garantindo que todas as IAs tenham acesso ao mesmo contexto estratégico.

---

## Pendências e próximos passos

### Bugs Conhecidos

| Bug | Prioridade | Status |
|---|---|---|
| Botão "Pausar" não funciona no Modo Colaborativo | Média | Pendente — investigar backend |
| Timeout na consolidação não implementado | Média | Pendente — adicionar `Promise.race` na consolidação |
| Gemini pode dar erro no Modo Colaborativo | Alta | Pendente — testar para identificar erro específico |
| Materiais gerando 15 seções vs 37-40 esperadas | Alta | Em investigação — prompts atualizados, aguardando teste |

### Próximos Passos Imediatos

1. **Testar Modo Colaborativo** com os novos prompts simplificados para validar se materiais voltaram a ter 28-30+ seções
2. **Exportar código para GitHub** via Settings → GitHub no Management UI
3. **Verificar sincronização GitHub ↔ Manus** para desenvolvimento multi-plataforma (Manus + Claude Code + Cursor)

### Funcionalidades Futuras Planejadas

- Indicador visual de "Cache Hit" no frontend
- Timeout na etapa de consolidação (atualmente só nas IAs individuais)
- Corrigir botão "Pausar" no Modo Colaborativo
- Relatórios mensais automáticos via `systemChangelog`
- Integração com WhatsApp para notificações (estrutura de banco já criada)
- Stripe para monetização (estrutura preparada mas não ativada)

---

## Arquivos e artefatos

### Estrutura do Projeto

```
ark-control-panel/
├── client/
│   ├── src/
│   │   ├── pages/                          # 12 páginas
│   │   │   ├── Home.tsx                    # Página principal com 3 modos
│   │   │   ├── Dashboard.tsx               # Analytics gerais
│   │   │   ├── Dashboards.tsx              # Hub de dashboards
│   │   │   ├── SessionsDashboard.tsx       # Histórico de sessões
│   │   │   ├── APIMonitoringDashboard.tsx  # Monitoramento de APIs
│   │   │   ├── DeveloperModePage.tsx       # Modo Desenvolvedor
│   │   │   ├── GuestManagement.tsx         # Gerenciamento de convidados
│   │   │   ├── NotificationSettings.tsx    # Configurações de notificação
│   │   │   ├── DocumentGenerator.tsx       # Geração de documentos ARK Strategy
│   │   │   ├── login.tsx                   # Página de login
│   │   │   ├── NotFound.tsx                # 404
│   │   │   └── ComponentShowcase.tsx       # Showcase de componentes
│   │   ├── components/                     # 30 componentes
│   │   │   ├── IntelligentCollaboration.tsx # Modo Colaborativo principal
│   │   │   ├── ProgressPanel.tsx           # Painel de progresso das IAs
│   │   │   ├── LiveFeed.tsx                # Feed em tempo real
│   │   │   ├── FormatSelector.tsx          # Seletor PDF/Word/PPT/Slides
│   │   │   ├── CollapsibleDocuments.tsx    # Bíblia ARK (documentos de contexto)
│   │   │   ├── TemplateGallery.tsx         # Galeria de templates
│   │   │   ├── DeveloperMode.tsx           # Interface do Modo Developer
│   │   │   ├── CacheManager.tsx            # Gerenciamento de cache
│   │   │   ├── CostsDashboard.tsx          # Dashboard de custos
│   │   │   ├── MaterialHistory.tsx         # Histórico de materiais
│   │   │   └── ... (20 componentes adicionais)
│   │   └── App.tsx                         # 9 rotas registradas
│   └── index.html
├── server/
│   ├── routers.ts                          # Endpoints tRPC (arquivo principal)
│   ├── db.ts                               # Query helpers Drizzle
│   ├── storage.ts                          # Helpers S3
│   ├── lib/
│   │   ├── intelligent-collaboration.ts    # Lógica core do Modo Colaborativo
│   │   ├── collaborative-agents.ts         # Agentes colaborativos
│   │   ├── orchestrator.ts                 # Lógica do Modo Orquestrador
│   │   ├── manus-client.ts                 # Cliente da API Manus
│   │   ├── pdf-generator.ts                # Gerador de PDF com branding ARK
│   │   ├── docx-generator.ts               # Gerador de Word com branding ARK
│   │   ├── pptx-generator.ts               # Gerador de PowerPoint com branding ARK
│   │   ├── manus-slides-generator.ts       # Gerador de Nano Banana slides
│   │   ├── document-manager.ts             # Gerenciador de documentos (Bíblia ARK)
│   │   ├── api-monitoring.ts               # Monitoramento de uso de APIs
│   │   ├── advanced-orchestration.ts       # Orquestração avançada
│   │   ├── consolidation-cache.ts          # Cache de consolidações
│   │   ├── task-complexity.ts              # Análise de complexidade de tarefas
│   │   ├── code-applier.ts                 # Aplicador de código (Modo Developer)
│   │   ├── logger.ts                       # Sistema de logs
│   │   ├── log-stream.ts                   # Streaming de logs
│   │   ├── timeout-wrapper.ts              # Wrapper de timeout com Promise.race
│   │   ├── checkpoint-manager.ts           # Gerenciador de checkpoints
│   │   └── notification-service.ts         # Serviço de notificações
│   └── _core/                              # Framework (não editar)
├── drizzle/
│   ├── schema.ts                           # 18 tabelas definidas
│   ├── relations.ts                        # Relações entre tabelas
│   └── 0000-0021 migrations               # 22 migrations aplicadas
├── docs/
│   ├── ark-strategy-templates/             # 5 templates + README
│   └── strategic-plans/                    # Versionamento de planos estratégicos
└── server/*.test.ts                        # 10 arquivos de teste (Vitest)
```

### Banco de Dados — 18 Tabelas

| Tabela | Função |
|---|---|
| `users` | Autenticação OAuth (roles: guest/user/admin) |
| `conversations` | Comandos executados |
| `aiResponses` | Respostas individuais de cada IA |
| `commandTemplates` | Templates de comandos pré-configurados |
| `conversationTags` | Tags de conversas (many-to-many) |
| `orchestrations` | Orquestrações complexas |
| `orchestrationTasks` | Subtarefas de orquestrações |
| `responseCache` | Cache de respostas (hash MD5) |
| `costs` | Monitoramento de custos por IA |
| `sessions` | Sessões persistentes com IAs externas |
| `documents` | Documentos da Bíblia ARK |
| `materials` | Materiais gerados (apresentações, planos, análises) |
| `collaborationSessions` | Sessões do Modo Colaborativo |
| `devSessions` | Sessões do Modo Desenvolvedor |
| `accessInvites` | Convites de acesso com código único |
| `guestSettings` | Permissões granulares para convidados |
| `notificationSettings` | Configurações de notificação |
| `notificationHistory` | Histórico de notificações enviadas |
| `systemChangelog` | Changelog do sistema |
| `apiUsageLogs` | Logs de uso de APIs |
| `consolidationCache` | Cache de consolidações (hash SHA256) |
| `documentTemplates` | Templates ARK Strategy |
| `generatedDocuments` | Documentos gerados a partir de templates |

### Checkpoints Salvos (histórico de versões)

| Versão | Data | Descrição |
|---|---|---|
| `704bbe85` | ~15 Jan | Consolidação em cascata com 4 estratégias |
| `a27f81fe` | ~15 Jan | Correção: consolidação resumindo demais (max_tokens aumentado) |
| `64738232` | ~16 Jan | Correções de UX e especialização das IAs |
| `4492b7de` | ~17 Jan | Consolidação gerando documentos completos (prompt reescrito) |
| `40f9133e` | ~18 Jan | Restauração do prompt antigo (37-40 seções) |
| `ba74dc60` | ~19 Jan | Redesenho completo das especializações das 4 IAs |
| `6c063624` | 20 Jan | Timeout REAL do Claude + botão Cancelar |
| `900fd597` | 26 Jan | Sistema de versionamento de documentos estratégicos |
| `518e1e98` | 27 Jan | Templates ARK Strategy v1.0 (5 templates + testes) |
| `54ce4fba` | 29 Jan | Manus "Desabilitado" (badge amarelo) |
| `28d66974` | 29 Jan | Sprint 3: DocumentGenerator + feedback visual + cache Gemini |
| `3d320452` | 29 Jan | Correções Gemini/Manus (logs de debug) |
| `1341e787` | 29 Jan | Gemini `gemini-2.0-flash` + endpoint diagnóstico |
| `0195ab8b` | 30 Jan | Prompts com liberdade total (25-30+ seções) |

### Secrets/Variáveis de Ambiente Configuradas

| Variável | Uso |
|---|---|
| `OPENAI_API_KEY` | API GPT-4o |
| `ANTHROPIC_API_KEY` | API Claude |
| `GOOGLE_API_KEY` | API Gemini 2.0-flash |
| `MANUS_API_KEY` | API Manus |
| `MANUS_PROJECT_ID` | Projeto Manus para sessões persistentes |
| `MANUS_TOPIC_ID` | Tópico Manus |
| `JWT_SECRET` | Assinatura de cookies de sessão |
| `DATABASE_URL` | Conexão MySQL/TiDB |
| `VITE_APP_TITLE` | "ARK Technology Control Panel" |

---

*Documento gerado em 14 de fevereiro de 2026 por Manus AI para documentação de contexto do projeto ARK Control Panel.*

---

## 3. Expansão do Sistema de Metas 2026 + Pesquisa Educacional Dubai

**Data:** 29 de Janeiro de 2026  
**Status:** Concluída  
**Projeto relacionado:** Portes Family (Vg5MNFDfPASJaQBXj97Ssv) - marcos_personal_dashboard

---

### O que foi feito

**1. Sistema de Metas 2026 - Expansão e Correções**

Mescladas metas antigas (30) com novas (15) totalizando 45 metas quantificáveis em 6 categorias (Espiritual, Profissional, Corpo, Social, Sentimental, Financeiro). Estrutura do banco de dados mantida conforme schema existente em `drizzle/schema.ts` com tabela `goals` contendo campos: id, userId, category, title, target, current, unit, createdAt, updatedAt.

Executadas 3 correções específicas via SQL direto:
- "Treinar pelo menos 4 vezes na semana" → "Fazer 200 treinos no ano" (target: 200)
- "Recuperar meus Joelhos" → "10 sessões de fisioterapia" (target: 10)
- Meta "Vender e Intermediar mais de 100M de AED" recebeu botões múltiplos (+10k, +50k, +100k, +500k, +1M)

Interface `/goals` otimizada para mobile com ajustes em `client/src/pages/Goals.tsx`:
- Grid responsivo: `grid-cols-1 md:grid-cols-2 lg:grid-cols-3`
- Padding reduzido em mobile: `p-4 md:p-6`
- Tamanhos de fonte ajustados: `text-xl md:text-2xl` para títulos
- Botões múltiplos implementados com lógica condicional baseada em `goal.id`

Testes unitários criados:
- `server/goals.expansion.test.ts` (validação de 45 metas)
- `server/goals.corrections.test.ts` (validação de nomes corrigidos e botões múltiplos)

**2. Documentação Técnica do Sistema**

Gerados 3 documentos PDF completos para compartilhamento com Claude:
- `DOCUMENTACAO_COMPLETA_SISTEMA_METAS_2026.pdf` (716 KB) - Sumário executivo, 45 metas detalhadas, arquitetura técnica, estrutura DB, funcionalidades UI, histórico de desenvolvimento
- `DIAGRAMAS_TECNICOS.pdf` (256 KB) - Diagramas ASCII de arquitetura (Frontend → tRPC → Backend → DB), fluxos de incremento, autenticação OAuth, modelo ER, responsividade
- `GUIA_RAPIDO_CLAUDE.pdf` (489 KB) - TL;DR, lista rápida das 45 metas, estrutura do projeto, arquivos principais, comandos úteis, consultas SQL prontas

**3. Pesquisa Deep Research - Educação em Dubai**

Realizada pesquisa profunda sobre educação para Luca (16 anos, 1º EM parado em maio/2025) e Davi (11 anos, 4ª série parada em maio/2025), ambos sem conhecimento de inglês.

**Cursos de Inglês identificados:**
- British Council UAE - Dubai Teaching Centre (Oud Metha, 5-7 min de Al Jadaf)
  - Secondary Plus (12-17 anos) para Luca: AED 4,295, Term 3 (29 Mar - 28 Jun 2026), 42h, nível Starter (Pre-A1)
  - Primary Plus (6-12 anos) para Davi: AED 4,295, Term 3 (29 Mar - 28 Jun 2026), 42h, nível Starter (Pre-A1)
  - General English para Luana: AED 4,200-5,250, nível Beginner (A1)

**Escolas Regulares analisadas:**
- South View School (Remraam, Dubailand) ⭐ RECOMENDADA
  - Luca: Year 11 (por idade: 16a 6m em 01/09/2026)
  - Davi: Year 6 (por idade: 11a 10m em 01/09/2026)
  - Programa EAL com 4 níveis (Intensive Pull-Out → Language Pull-Out → In-Class Support → Monitoring)
  - Custo: AED 94,194 no 1º ano (~$25,700), AED 92,194/ano seguintes
  - Desconto 5% no 2º filho (Davi)
- Dunecrest American School (Dubailand): AED 155,920/ano (~$42,500) - descartada por custo
- Jebel Ali School (DAMAC Hills): AED 99,000/ano (~$27,000) - lista de espera

**Documentação gerada:**
- `GUIA_COMPLETO_EDUCACAO_DUBAI_FAMILIA_PORTES.pdf` (474 KB) - Documento único consolidado com 6 seções: Cursos de Inglês, Escolas Regulares, Documentação Necessária, Cronograma (Fev-Ago 2026), Contatos/Endereços, Resumo Financeiro

---

### Decisões técnicas relevantes

**Sistema de Metas:**
- Mantida estrutura de banco existente sem alterações de schema
- Botões múltiplos implementados via lógica condicional no frontend (não no backend) para evitar complexidade desnecessária
- Incrementos customizados baseados em `goal.id` específico da meta de AED
- Responsividade mobile-first com breakpoints Tailwind padrão (md: 768px, lg: 1024px)

**Pesquisa Educacional:**
- Priorizada South View School por custo-benefício (economia de $84,000 em 5 anos vs Dunecrest)
- British Council escolhido por ser único local com programas para crianças (6-12), teenagers (12-17) e adultos simultaneamente
- Estratégia de preparação: 4 meses de inglês intensivo (Mar-Jun) antes da matrícula escolar (Ago)
- Enquadramento por idade confirmado via documento oficial "ENROLMENT GUIDELINES ACADEMIC YEAR 2025-2026.pdf" da South View

---

### Pendências e próximos passos

**Sistema de Metas:**
1. Implementar botões +5 e +10 para metas médias (Cultos: 35, Dias com Filhos: 36, Livros da Bíblia: 66)
2. Adicionar campo de input manual para valores customizados
3. Criar histórico de incrementos (últimos 5 registros por meta com data/hora)
4. Implementar filtros por progresso ("Não iniciadas", "Em progresso", "Perto da meta")
5. Sistema de notificações semanais via email para metas com 0% ou abaixo da média esperada

**Educação Dubai:**
1. **Esta semana (17-23 Fev):**
   - Ligar 600 529 995 (British Council) para agendar teste de nivelamento
   - Solicitar Transfer Certificate das escolas no Brasil (Luca e Davi)
   - Preencher application form online da South View School
2. **Fev-Mar:** Apostilar Transfer Certificates no Brasil (Apostila de Haia)
3. **Mar:** Iniciar cursos de inglês (29 Março 2026)
4. **Abr-Mai:** Assessment na South View School + aceitar oferta + pagar deposit
5. **Jun-Jul:** KHDA Registration + comprar uniformes/materiais
6. **Ago:** Início do ano letivo 2026-2027

---

### Arquivos e artefatos

**Sistema de Metas (marcos_personal_dashboard):**
- `client/src/pages/Goals.tsx` - Interface otimizada para mobile com botões múltiplos
- `server/goals.expansion.test.ts` - Testes de validação das 45 metas
- `server/goals.corrections.test.ts` - Testes de correções de nomes e botões
- `todo.md` - Rastreamento de features (todas marcadas como [x])
- Checkpoints: `7f0a8c65` (inicial), `03c02705` (expansão 45 metas), `85512857` (correções finais)
- Preview: https://3000-is8eqhtyhhej3rtgk9opi-668991c1.sg1.manus.computer/goals

**Documentação Técnica:**
- `/home/ubuntu/DOCUMENTACAO_COMPLETA_SISTEMA_METAS_2026.pdf` (716 KB)
- `/home/ubuntu/DIAGRAMAS_TECNICOS.pdf` (256 KB)
- `/home/ubuntu/GUIA_RAPIDO_CLAUDE.pdf` (489 KB)

**Pesquisa Educacional:**
- `/home/ubuntu/GUIA_COMPLETO_EDUCACAO_DUBAI_FAMILIA_PORTES.pdf` (474 KB) - Documento consolidado final
- `/home/ubuntu/DOCUMENTO_1_ESCOLAS_REGULARES_DUBAI_ATUALIZADO.pdf` (422 KB) - Versão intermediária
- `/home/ubuntu/DOCUMENTO_2_CURSOS_INGLES_MARCO_2026_ATUALIZADO.pdf` (484 KB) - Versão intermediária
- `/home/ubuntu/pesquisa_educacao_dubai.md` - Notas de pesquisa brutas
- `/home/ubuntu/enquadramento_idade_escolas.md` - Análise de enquadramento Year/Grade
- `/home/ubuntu/british_council_secondary_plus.md` - Detalhes do programa Secondary Plus

**Contatos Principais:**
- British Council Dubai: 600 529 995 | WhatsApp +971 269 10639 | Oud Metha
- South View School: admissions@southview.ae | +971 4 361 8099 | Remraam, Dubailand

**Custos Totais (1º Ano 2026-2027):**
- Cursos de Inglês: AED 12,790-13,840 (~$3,480-$3,770)
- Escola Regular: AED 94,194 (~$25,700)
- Total sem transporte: AED 110,584-116,634 (~$30,110-$32,155)

---

## 4. Criação de Plano de Investimento em Criptoativos — ARK Financial (Cliente: José Blesa)

**Data:** 09 de fevereiro de 2026  
**Status:** Concluída  
**Projeto relacionado:** ARK Group - ARK Financial (Advisory de Investimentos)

---

## O que foi feito

### 1. Análise e Estruturação do ARK Group
- Revisão completa dos documentos do projeto ARK Group (13 arquivos compartilhados)
- Identificação da estrutura do grupo: ARK Strategy, ARK Commercial, ARK Financial, ARK Technology, ARK Makers
- Análise do posicionamento da ARK Financial como **advisor financeiro** (não gestora de fundos)
- Documentação consolidada do grupo em `/home/ubuntu/ark_group_consolidated_document.md`

### 2. Desenvolvimento do Plano de Investimento
**Cliente:** José Antonio Blesa Blanco (Espanhol, Passaporte PAM043200, DNI 75269047Y)

**Estratégia definida:**
- Aporte mensal: USD 15.000
- Aportes esporádicos adicionais (valores variáveis)
- Horizonte: 5 anos
- Metodologia: Dollar-Cost Averaging (DCA) + LOAN estratégico (10%, 20% ou 30% em ocasiões especiais)

**Alocação de ativos:**
- 50% BTC (Hedge da carteira)
- 30% ETH (Fundamento sólido)
- 10% SOL (Potencializador)
- 10% XRP (Potencializador)

**Projeções calculadas (5 anos):**
- Cenário Conservador (25% CAGR): $2.2M (1.93x)
- Cenário Moderado (44% CAGR): $3.6M (3.11x)
- Cenário Otimista (63% CAGR): $5.6M (4.88x)

**Arquivos gerados:**
- `/home/ubuntu/plano_financeiro_jose_blesa_final.md` (Português)
- `/home/ubuntu/plano_financeiro_jose_blesa_final.pdf` (Português)
- `/home/ubuntu/plan_financiero_jose_blesa_final_es.md` (Espanhol)
- `/home/ubuntu/plan_financiero_jose_blesa_final_es.pdf` (Espanhol)

### 3. Pesquisa de Mercado e Fundamentação
- Análise histórica dos últimos 5 anos de BTC, ETH, SOL e XRP via Yahoo Finance API
- Identificação de descontos significativos em relação aos ATH:
  - BTC: 43% de desconto
  - ETH: 56% de desconto
  - SOL: 65% de desconto
  - XRP: 60% de desconto
- Pesquisa de previsões de mercado (Google Gemini AI predictions para 2026)
- Script Python: `/home/ubuntu/crypto_historical_analysis.py`
- Gráficos gerados: `/home/ubuntu/projection_scenarios_v2.png`

### 4. Infraestrutura de Custódia e Segurança
**Estratégia em 2 Fases:**

**FASE 1 - Início Imediato (Semana 1):**
- MetaMask compartilhada (seed phrase compartilhada entre advisor e cliente)
- Início dos aportes sem delay
- Duração máxima: 2 semanas

**FASE 2 - Estrutura Profissional (Semanas 2-3):**
- Migração para carteiras multisig por ativo:
  - ETH → Safe (Gnosis Safe) - 2-de-2
  - SOL → Squads Protocol - 2-de-2
  - BTC → Nunchuk - 2-de-3 (com backup)
  - XRP → Xaman Multisig - 2-de-2
- Aprovação dupla obrigatória (cliente + ARK Financial)

**Pesquisa realizada:**
- Análise da BitGo (descartada por não ser self-custody puro)
- Comparação de soluções multisig para cada blockchain
- Documentos gerados:
  - `/home/ubuntu/solucoes_multisig_aprovacao_dupla.md`
  - `/home/ubuntu/analise_bitgo_e_recomendacoes.pdf`
  - `/home/ubuntu/estrategia_implementacao_duas_fases.pdf`

### 5. Estratégia de Staking e Yield
**Decisões tomadas:**
- **ETH (30%):** Staking com Lido (2.8% APY) - **IMPLEMENTADO**
  - 2.3182 stETH em staking
  - Plataforma: https://lido.fi/
- **BTC (50%):** Deixar parado (segurança máxima, 0% yield)
  - Avaliado WBTC + Aave (2-5% APY) mas descartado por complexidade de conversão
- **SOL (10%):** Deixar parado (MetaMask não suporta Solana nativamente)
- **XRP (10%):** Deixar parado (não há protocolo tipo Lido ainda)

**Impacto estimado:** +$50K-$100K em 5 anos apenas com staking de ETH

**Documentos:**
- `/home/ubuntu/guia_staking_yield_cripto.pdf`

### 6. Contrato de Prestação de Serviços
**Estrutura jurídica:**
- Contratada: Marcos Paulo Rezende Portes (pessoa física) como Advisor
- Cláusula de transferência futura para ARK Financial quando formalizada
- Foro: Dubai (DIFC)

**Remuneração:**
- Setup Fee: USD 2.200 (pagamento único) - **PAGO em 08/02/2026**
- Performance Fee: 10% sobre lucro líquido mensal (apuração todo dia 1º)

**Proteções legais:**
- Natureza consultiva (não gestão discricionária)
- Custódia do cliente (non-custodial)
- Isenção de responsabilidade robusta sobre volatilidade de mercado

**Arquivos:**
- `/home/ubuntu/contrato_consultoria_jose_blesa_final_es.pdf` (Espanhol, com dados preenchidos)
- Layout profissional com bandeiras dos EAU, campos de assinatura

### 7. Apresentações Executivas (Nano Banana)
**Tema:** Financeiro Sofisticado - Minimalismo Premium
- Paleta: Azul profundo (#1e3a5f), dourado (#d4af37), verde (#10b981), vermelho (#ef4444)
- Tipografia: Space Grotesk (títulos), Inter (corpo)
- 18 slides com storytelling completo

**Versões criadas:**
- **Português:** `manus-slides://NJhbBHrJkwBmeD48OUaAxB`
  - Projeto: `/home/ubuntu/ark_financial_presentation/`
- **Espanhol:** `manus-slides://sLLscIC5tfo9r5v9MEIsEx`
  - Projeto: `/home/ubuntu/ark_financial_presentation_es/`

**Estrutura:**
1. Capa institucional
2. Sumário executivo
3. Filosofia de investimento
4. Composição do portfólio (50/30/10/10)
5. Análise de desconto dos ativos
6. Fundamentos: Bitcoin (hedge)
7. Fundamentos: Ethereum (base sólida)
8. Fundamentos: SOL + XRP (potencializadores)
9. Projeções de crescimento (3 cenários)
10. Evolução patrimonial (tabela 5 anos)
11. Gráfico de projeção visual
12. Gestão de risco e volatilidade
13. Estratégia de implementação (2 fases)
14. Fase 1: MetaMask compartilhada
15. Fase 2: Multisig profissional
16. Cronograma de implementação
17. Próximos passos
18. Conclusão e call-to-action

**Roteiro:** `/home/ubuntu/roteiro_storytelling_apresentacao_ark_financial.pdf`

### 8. Implementação Prática
**Carteiras criadas:**
- MetaMask (celular): Carteira compartilhada para José Blesa
- Xaman (celular): Carteira XRP para José Blesa
  - Endereço: rJ7knUtVVxCTC4V2Uu1nwTBZTthCTHELHP
  - Nome: BlesaWalletXRP

**Guias práticos gerados:**
- `/home/ubuntu/guia_metamask_celular.pdf` (12 passos para criar MetaMask no celular)
- `/home/ubuntu/guia_xaman_computador.pdf` (guia Xaman para desktop/mobile)

**Transações executadas (06/02/2026):**
- Compra de 42,512 SOL por $3.585,36 (custo médio: $84,34/SOL)
- Compra de 2,328 ETH por $4.628,57 (custo médio: $1.987,95/ETH)
- Compra de 1.992 XRP por $2.929,97 (custo médio: $1,4709/XRP)
- **Total investido:** $11.143,90

**Staking implementado (09/02/2026):**
- 2.3182 ETH depositados no Lido
- Recebido: 2.3182 stETH
- APY atual: 2.8%

### 9. Perfil do Cliente e Documentação
**Arquivo mestre:** `/home/ubuntu/perfil_cliente_jose_blesa_atualizado.pdf`

**Posição atual (09/02/2026 às 01:49):**
- **BTC:** 0,258 BTC = $18.278,35
- **ETH:** 2,318 ETH (stETH) = $4.880,48
- **SOL:** 42,51 SOL = $3.698,34
- **XRP:** 1.990,60 XRP = $2.843,21
- **USDT:** 7.671,47 USDT = $7.666,15
- **Total:** $37.366,53

**Performance (3 dias):**
- ETH: +$251,91 (+5,44%) ✅
- SOL: +$112,98 (+3,15%) ✅
- XRP: -$86,76 (-2,96%) ⚠️
- **Total P&L:** +$278,13 (+2,49%) ✅

**Histórico completo de transações documentado:**
- Janeiro 2026: Conversões USDT/AED
- 06/02: Compras iniciais (SOL, ETH, XRP)
- 08/02: Pagamento Setup Fee ($2.200)
- 09/02: Staking ETH no Lido

---

## Decisões técnicas relevantes

### Arquitetura de Custódia
**Decisão:** Abordagem híbrida em 2 fases (MetaMask → Multisig)
- **Justificativa:** Balancear velocidade de entrada no mercado (não perder oportunidade) com segurança de longo prazo
- **Trade-off:** Risco temporário de custódia compartilhada (seed phrase) vs. delay de 2-3 semanas para setup multisig completo
- **Mitigação:** Prazo máximo de 2 semanas + comunicação clara ao cliente sobre transição

### Seleção de Protocolos de Staking
**Decisão:** Apenas Lido para ETH, demais ativos parados
- **Justificativa:** 
  - Lido é o protocolo mais auditado e seguro (baixo risco)
  - BTC não tem staking nativo (WBTC + Aave tem complexidade e risco de smart contract)
  - SOL não funciona na MetaMask (requer Phantom)
  - XRP não tem protocolo tipo Lido ainda
- **Trade-off:** Yield médio de ~1% APY vs. segurança máxima
- **Impacto:** Conservadorismo adequado para cliente de alto patrimônio

### Estrutura Jurídica
**Decisão:** Contrato como pessoa física com cláusula de sucessão para ARK Financial
- **Justificativa:** ARK Financial ainda não está formalizada
- **Risco:** Menor proteção patrimonial para o advisor
- **Mitigação:** Cláusula de transferência automática quando empresa for constituída

### Alocação de Ativos
**Decisão:** 50% BTC, 30% ETH, 10% SOL, 10% XRP
- **Justificativa:** 
  - BTC como hedge e reserva de valor (50%)
  - ETH como fundamento tecnológico (30%)
  - SOL e XRP como potencializadores com alto desconto (20%)
- **Revisão:** Alocação será revista a cada nova compra conforme momento de mercado

### Projeções de Retorno
**Decisão:** Usar dados históricos reais dos últimos 5 anos + análise de desconto
- **Metodologia:** 
  - Cenário Conservador: 25% CAGR (abaixo da média histórica)
  - Cenário Moderado: 44% CAGR (média histórica ajustada)
  - Cenário Otimista: 63% CAGR (recuperação aos ATH)
- **Rejeição:** Descartado uso de projeções genéricas (25/50/75%) sem fundamentação

---

## Pendências e próximos passos

### Curto Prazo (Próximas 2 Semanas)
1. **Migração para Multisig (Fase 2):**
   - [ ] Criar carteira Safe (Gnosis) para ETH
   - [ ] Criar carteira Squads para SOL
   - [ ] Criar carteira Nunchuk para BTC
   - [ ] Configurar Xaman Multisig para XRP
   - [ ] Transferir ativos da MetaMask para carteiras multisig
   - [ ] Testar fluxo de aprovação dupla

2. **Primeiro Aporte Mensal:**
   - [ ] Receber USD 15.000 do cliente (data: 01/03/2026)
   - [ ] Executar compras conforme alocação (50/30/10/10)
   - [ ] Documentar transações no perfil do cliente

3. **Primeira Apuração de Performance:**
   - [ ] Calcular P&L mensal (01/03/2026)
   - [ ] Calcular Performance Fee (10% sobre lucro)
   - [ ] Emitir relatório mensal para o cliente

### Médio Prazo (1-3 Meses)
4. **Otimização de Yield:**
   - [ ] Avaliar staking de SOL via Phantom + Jito (se cliente aprovar)
   - [ ] Avaliar WBTC + Aave para BTC (se cliente aprovar)
   - [ ] Monitorar lançamento de protocolos de yield para XRP

5. **Formalização da ARK Financial:**
   - [ ] Constituir ARK Financial como empresa em Dubai (DMCC)
   - [ ] Transferir contrato de pessoa física para ARK Financial
   - [ ] Atualizar documentação legal

6. **Modelagem de Cenários:**
   - [ ] Criar modelo de LOAN estratégico (10%, 20%, 30%)
   - [ ] Definir gatilhos para aportes esporádicos adicionais
   - [ ] Simular impacto de "pumps" trimestrais/semestrais

### Longo Prazo (3-12 Meses)
7. **Expansão de Serviços:**
   - [ ] Criar modelo replicável para novos clientes
   - [ ] Desenvolver dashboard de acompanhamento em tempo real
   - [ ] Integrar APIs de exchanges para automação de compras

8. **Oportunidades Específicas:**
   - [ ] Monitorar lançamento da SpaceX (ações)
   - [ ] Avaliar migração para carteiras institucionais (Fireblocks, Copper)
   - [ ] Explorar estratégias de tax optimization (Dubai)

### Bugs Conhecidos / Limitações
- **MetaMask não suporta SOL nativo:** Solana está sendo mantida como wrapped ou via exchange temporariamente
- **XRP não tem extensão oficial para Chrome:** Xaman é mobile-only, GemWallet é alternativa para desktop
- **BTC na MetaMask é Native SegWit, não WBTC:** Conversão para WBTC requer exchange ou bridge (complexo)

---

## Arquivos e artefatos

### Documentos Estratégicos
- `/home/ubuntu/ark_group_consolidated_document.md` - Bíblia do ARK Group atualizada
- `/home/ubuntu/plano_financeiro_jose_blesa_final.pdf` - Plano completo (PT)
- `/home/ubuntu/plan_financiero_jose_blesa_final_es.pdf` - Plano completo (ES)
- `/home/ubuntu/perfil_cliente_jose_blesa_atualizado.pdf` - Perfil mestre do cliente

### Contratos e Documentos Legais
- `/home/ubuntu/contrato_consultoria_jose_blesa_final_es.pdf` - Contrato assinável (ES)
- Dados do cliente: José Antonio Blesa Blanco (DNI 75269047Y, Passaporte PAM043200)
- Dados do advisor: Marcos Paulo Rezende Portes (Emirates ID 784-1990-2710212-0, Passaporte FY284219)

### Apresentações (Nano Banana)
- `manus-slides://NJhbBHrJkwBmeD48OUaAxB` - Apresentação em Português (18 slides)
- `manus-slides://sLLscIC5tfo9r5v9MEIsEx` - Apresentação em Espanhol (18 slides)
- `/home/ubuntu/roteiro_storytelling_apresentacao_ark_financial.pdf` - Roteiro completo

### Análises e Pesquisas
- `/home/ubuntu/crypto_historical_analysis.py` - Script de análise histórica (5 anos)
- `/home/ubuntu/financial_projection_v2.py` - Script de projeções (3 cenários)
- `/home/ubuntu/projection_scenarios_v2.png` - Gráfico de projeções
- `/home/ubuntu/pump_impact_comparison.png` - Gráfico de impacto de aportes extras
- `/home/ubuntu/analise_bitgo_e_recomendacoes.pdf` - Análise de soluções multisig

### Guias Práticos
- `/home/ubuntu/guia_metamask_celular.pdf` - Setup MetaMask (12 passos)
- `/home/ubuntu/guia_xaman_computador.pdf` - Setup Xaman
- `/home/ubuntu/guia_staking_yield_cripto.pdf` - Estratégias de staking
- `/home/ubuntu/estrategia_implementacao_duas_fases.pdf` - Roadmap de implementação

### Dados do Cliente
**Carteiras:**
- MetaMask: Account 1 (compartilhada)
- Xaman: BlesaWalletXRP (rJ7knUtVVxCTC4V2Uu1nwTBZTthCTHELHP)

**Posição Atual (09/02/2026):**
```
BTC:  0,258 BTC      = $18.278,35  (custo médio: N/A - não comprado ainda)
ETH:  2,318 stETH    = $4.880,48   (custo médio: $1.987,95/ETH)
SOL:  42,51 SOL      = $3.698,34   (custo médio: $84,34/SOL)
XRP:  1.990,60 XRP   = $2.843,21   (custo médio: $1,4709/XRP)
USDT: 7.671,47 USDT  = $7.666,15
-----------------------------------------------------
TOTAL:                 $37.366,53
```

**Transações:**
- 06/02/2026: Compras iniciais (SOL, ETH, XRP) - $11.143,90
- 08/02/2026: Pagamento Setup Fee - $2.200,00
- 09/02/2026: Staking ETH no Lido - 2.3182 stETH

**Performance (3 dias):**
- P&L: +$278,13 (+2,49%)

### Scripts e Ferramentas
- Python 3.11 com bibliotecas: yfinance, pandas, matplotlib, numpy
- WeasyPrint para geração de PDFs com layout profissional
- manus-md-to-pdf para conversão de Markdown
- APIs utilizadas: Yahoo Finance (dados históricos)

### Repositórios e Links
- Lido Finance: https://lido.fi/ (staking ETH)
- Aave: https://app.aave.com/ (avaliado para BTC, não implementado)
- Safe (Gnosis Safe): https://safe.global/ (multisig ETH - pendente)
- Squads Protocol: https://squads.so/ (multisig SOL - pendente)
- Xaman: https://xaman.app/ (carteira XRP)

---

**Observações Finais:**
- Cliente aprovou proposta e assinou contrato
- Setup Fee de $2.200 recebido em 08/02/2026
- Primeira compra executada em 06/02/2026
- Staking implementado em 09/02/2026
- Próximo milestone: Migração para multisig (até 20/02/2026)
- Próximo aporte: $15.000 em 01/03/2026

---

## 5. Criação de Apresentações Imobiliárias Premium para Clientes EAU + Análise Legal de Pagamento Internacional

**Data:** 09-10 de Fevereiro de 2026  
**Status:** Concluída  
**Projeto relacionado:** Ark Group - Apresentações Imobiliárias e Consultoria Legal

---

### O que foi feito

Esta sessão envolveu a criação de **três apresentações imobiliárias distintas** em espanhol para diferentes perfis de clientes, além de uma **análise legal técnica** sobre comprovação de pagamento internacional sob a legislação dos EAU.

#### 1. Apresentação Radisson Blu RAK + Orvessa Residences (Cliente Inicial)

**Objetivo:** Comparar dois projetos imobiliários em RAK e Dubai para investidor conservador.

**Projetos analisados:**
- **Radisson Blu RAK (Studio):** 527 Sq.Ft, AED 1,318,600 (USD 358k | EUR 316k)
  - Plano: 20% entrada + 50% obra (parcelas) + 30% entrega
  - DLD 4% pago **somente na entrega**
  - ROI 3 anos: 280% | Rental Yield: 10%
  
- **Orvessa Residences (1BR):** 720 Sq.Ft, AED 1,280,000 (USD 348k | EUR 306k)
  - Plano: 20% entrada + 50% obra (parcelas) + 30% entrega
  - DLD 4% pago **no início** (junto com entrada)
  - ROI 3 anos: 150% | Rental Yield: 7%

**Correções realizadas:**
- Ajuste do plano de pagamento de "20% booking + 10% down" para "20% down payment direto"
- Inclusão de valores em **3 moedas** (AED, USD, EUR) em todos os slides financeiros
- Destaque da diferença no timing do DLD 4% entre os projetos

**Arquivo gerado:** `Presentacion_Radisson_Orvessa_ES` (manus-slides://e88qIIz0cKbvc9rkvY8UiS → oL7gnuxllonJY9avJfgz3f)

---

#### 2. Apresentação Cliente Amador (Object-1 + DAMAC Valencia)

**Objetivo:** Apresentar 3 opções de entrada no mercado imobiliário de Dubai (faixa AED 750k - 1.13M).

**Projetos analisados:**

**A. Object-1 (Oferta Ramadan - Válida até 31 Mar 2026):**
- **Alta View Sky Homes (JVC):** 1BR, 735 Sq.Ft, AED 1,092,750 (com desconto de AED 82k)
  - Plano: 20% entrada + Parcelas mensais (0.25%) + 2 Balões (6%) + 30% entrega
  - DLD 4% pago na entrega
  
- **Elaris Sky (JVT):** 1BR, 720 Sq.Ft, AED 1,134,600 (com desconto de AED 85k)
  - Plano: Igual ao Alta View
  - DLD 4% pago na entrega

**B. DAMAC Valencia (Lagoons - Pré-Venda até 03/02/2026):**
- **Studio:** AED 750,000 (EOI: AED 35k)
- **1BR:** AED 1,300,000 (EOI: AED 55k)
- **2BR:** AED 1,840,000 (EOI: AED 90k)
- Plano: **60/40** (15% entrada + 45% obra em 9 parcelas trimestrais de 5% + 40% entrega)
- DLD 4% pago no início
- **Mecânica EOI:** O valor da Expression of Interest (EOI) é **abatido** do total da entrada (15% + 4% DLD)

**Decisões técnicas importantes:**
1. **Regra de EOI:** Estabelecido que a EOI sempre abate da entrada inicial, seja 15% ou 20% (padrão de mercado nos EAU).
2. **Alerta de Preço:** Incluído aviso de que preços "a partir de" podem sofrer ágio de 8-10% para unidades premium.
3. **Tabelas de Pagamento Detalhadas:** Criadas tabelas completas mostrando:
   - Entrada total (Down Payment + DLD + Registro)
   - Parcelas mensais/trimestrais (valor exato e datas)
   - Balões intermediários (quando aplicável)
   - **Saldo Final na Entrega** (valor exato para quitação)

**Correções realizadas:**
- Plano DAMAC corrigido de "20% entrada" para "15% entrada + 60/40"
- Implementação da mecânica de EOI abatida (Entrada Total - EOI = Saldo a Pagar Agora)
- Conversão de todas as etapas de pagamento para 3 moedas (AED, USD, EUR)

**Arquivo gerado:** `Presentacion_Cliente_Amador_ES` (manus-slides://ivDmey1ATCYZpgRGS9K7Ly → oL7gnuxllonJY9avJfgz3f)

---

#### 3. Apresentação Premium Cliente Fábio (DAMAC Islands 2 + The Valley Amelia)

**Objetivo:** Material Ultra Luxury focado em lifestyle, exclusividade e patrimônio familiar (faixa AED 2.8M - 9.6M).

**Projetos analisados:**

**A. DAMAC Islands 2 (Barbados - Arquipélago Tropical):**
- **Villa 4BR (DIBR1):** 2,185 Sq.Ft, AED 2,824,000 (USD 769k)
  - Plano: 75/25 (Parcelas mensais de 1% + trimestrais de 3%)
  - Entrega: Junho 2030
  
- **Villa 5BR:** 3,000+ Sq.Ft, AED 3,959,000 (USD 1.08M)
  - Plano: Similar ao 4BR
  - Valorização projetada: +70% em 5 anos

**B. The Valley Amelia (EMAAR - Oásis Familiar):**
- **Villa 4BR (V-13):** 4,356 Sq.Ft, AED 7,262,888 (USD 1.98M)
  - Plano: 80/20 (Parcelas semestrais de 10%)
  - Entrega: Dezembro 2029
  
- **Villa 5BR (V-132):** 5,500+ Sq.Ft, AED 9,662,888 (USD 2.63M)
  - Plano: Similar ao 4BR
  - Valorização projetada: +60% em 5 anos

**Estratégia de Design:**
- **Estilo:** "Ultra Luxury" (Branco, Dourado Champagne, Cinza Escuro)
- **Tipografia:** Playfair Display (títulos) + Montserrat (corpo)
- **Narrativa:** Foco em storytelling emocional ("Não é tijolo, é legado familiar")
- **Imagens:** Full-screen de alto impacto (águas cristalinas, dunas, interiores de luxo)

**Problema identificado e corrigido:**
- **Versão 1 (quebrada):** Arquivo exportado com 10x menos tamanho, imagens repetidas, texto em português, layout desconfigurado.
- **Diagnóstico:** Caminhos de imagem quebrados, falta de recursos visuais de alta resolução, texto não traduzido.
- **Solução:** Reconstrução completa da apresentação (V2) com:
  - Imagens contextuais únicas para cada slide
  - Texto 100% em espanhol
  - Layout robusto com caminhos de imagem absolutos

**Arquivos gerados:** 
- `Presentacion_Premium_Fabio_ES` (quebrada - descartada)
- `Presentacion_Premium_Fabio_ES_V2` (corrigida - manus-slides://4tOv2TrNqLAgWQilbmIVva)

---

#### 4. Análise Legal: Comprovação de Pagamento Internacional (Fábio Celestini - Tonino Lamborghini RAK)

**Contexto:** Cliente russo (Fábio Celestini) pagou entrada de AED 380,748 da Unidade 217 via intermediária (KNIGHTSBRIDGE INVESTMENT FZC) devido a restrições bancárias. Cliente solicitou confirmação de que os 2 documentos fornecidos são suficientes como comprovante.

**Documentos analisados:**
1. **Supplementary Agreement (23.01.2026):** Acordo entre BNW Real Estate Development LLC RAK Branch e Fábio Celestini, autorizando KNIGHTSBRIDGE como Payment Agent.
2. **Extrato Bancário Russo (05.02.2026):** Comprovante de transferência de RUB 8,025,881 (~AED 380,748) de Fábio para KNIGHTSBRIDGE via Bank Sinara.

**Fluxo de Pagamento Identificado:**
```
Fábio Celestini (OTP Bank Moscow) 
    → KNIGHTSBRIDGE INVESTMENT FZC (Bank Sinara, Rússia) 
    → Escrow Account (EAU) 
    → BNW Real Estate Development LLC RAK
```

**Base Legal Pesquisada:**
- **Dubai Law No. 8 of 2007 Concerning Escrow Accounts for Real Estate Development**
  - Artigo 6: Obrigação de desenvolvedores abrirem Escrow Account para projetos off-plan
  - Artigo 7: Todos os pagamentos de compradores devem ser depositados na Escrow Account
  - Artigo 9: Fundos protegidos contra penhora de credores do desenvolvedor
  - Artigo 11: Dubai Land Department (DLD) fiscaliza e audita as contas regularmente
  - Artigo 14: Banco retém 5% até 1 ano após registro das unidades em nome dos compradores (incentivo legal para desenvolvedor registrar as unidades)
  - Artigo 15: Proteção em caso de emergência (reembolso ou conclusão do projeto)

**Conclusão Legal:**
Os 2 documentos são **suficientes** porque:
1. Comprovam que Fábio cumpriu sua obrigação contratual (acordo + execução do pagamento).
2. A Dubai Law No. 8 of 2007 **obriga** a BNW a depositar os fundos na Escrow Account (não pode desviar).
3. O DLD fiscaliza e audita o processo automaticamente (proteção governamental).
4. A BNW é **obrigada** a registrar a unidade em nome de Fábio para receber os 5% finais retidos pelo banco.
5. O sistema legal dos EAU protege os direitos do comprador automaticamente, sem necessidade de comprovante adicional do repasse KNIGHTSBRIDGE → Escrow Account.

**Resposta técnica entregue:** Mensagem curta em espanhol para WhatsApp, explicando a suficiência dos documentos e a proteção legal automática.

**Arquivos gerados:**
- `/home/ubuntu/analise_pagamento_fabio_celestino.txt` (análise completa)
- `/home/ubuntu/dubai_escrow_law_key_findings.txt` (achados legais da Dubai Law No. 8 of 2007)

---

### Decisões técnicas relevantes

#### 1. Planos de Pagamento Imobiliários nos EAU

**Padrão Object-1 (20-50-30 com Parcelas Mensais + Balões):**
- 20% Down Payment (no início)
- 50% Durante a Obra:
  - Parcelas mensais de 0.25% (baixas e constantes)
  - 2 Balões de 6% cada (em marcos específicos da obra)
- 30% Na Entrega
- DLD 4% pago na entrega (diferencial competitivo)

**Padrão DAMAC (60/40 ou 70/30):**
- 15% Down Payment + 4% DLD (no início)
- 45% Durante a Obra (9 parcelas trimestrais de 5%)
- 40% Na Entrega

**Padrão EMAAR (80/20):**
- 20% Down Payment + 4% DLD (no início)
- 60% Durante a Obra (parcelas semestrais de 10%)
- 20% Na Entrega

**Regra de EOI (Expression of Interest):**
- A EOI é sempre **abatida** do total da entrada (Down Payment + DLD + Registro).
- Fórmula: `Saldo a Pagar Agora = (Down Payment % + DLD 4% + Registro) - EOI`
- Esta é uma regra de mercado padrão nos EAU para projetos em pré-venda.

#### 2. Conversão de Moedas

**Taxas utilizadas (Fevereiro 2026):**
- AED → USD: 0.2722 (1 AED = 0.2722 USD)
- AED → EUR: 0.2400 (1 AED = 0.2400 EUR)

**Decisão:** Todos os valores financeiros (preços, entradas, parcelas, saldos finais) devem ser apresentados em **3 moedas simultaneamente** (AED, USD, EUR) para facilitar a decisão de investidores internacionais.

#### 3. Estrutura de Tabelas de Pagamento

**Formato aprovado:**
```
┌─────────────────────┬─────────────┬─────────────┬─────────────┐
│ Etapa               │ AED         │ USD         │ EUR         │
├─────────────────────┼─────────────┼─────────────┼─────────────┤
│ Entrada (20%+DLD)   │ 307,200     │ 83,620      │ 73,728      │
│ Parcela Mensal (x)  │ 2,730       │ 743         │ 655         │
│ Balão 1 (6%)        │ 65,520      │ 17,831      │ 15,725      │
│ Balão 2 (6%)        │ 65,520      │ 17,831      │ 15,725      │
│ Saldo Final (30%)   │ 384,000     │ 104,525     │ 92,160      │
└─────────────────────┴─────────────┴─────────────┴─────────────┘
```

#### 4. Design de Apresentações Premium

**Hierarquia de Estilos:**
- **Cliente Amador:** "Quiet Luxury" (Branco, Dourado Suave, Cinza)
- **Cliente Premium:** "Ultra Luxury" (Branco, Dourado Champagne, Cinza Escuro)

**Regras de Imagens:**
- Cada slide deve ter imagem **contextual e única** (não repetir)
- Imagens de background devem ocupar **tela cheia** (full-screen)
- Usar caminhos de imagem **absolutos** (ex: `/home/ubuntu/projeto/imagem.png`)
- Evitar imagens genéricas de stock; priorizar imagens dos brochuras oficiais

**Tratamento de Erros de Renderização:**
- Se o arquivo exportado estiver "10x menor" que o esperado = imagens não carregaram
- Solução: Reconstruir projeto com caminhos absolutos e verificar disponibilidade de recursos visuais

#### 5. Legislação Imobiliária dos EAU

**Dubai Law No. 8 of 2007 - Pontos-Chave:**
- Escrow Account é **obrigatória** para todos os projetos off-plan
- Desenvolvedor **não pode** acessar fundos livremente (apenas conforme progresso da obra)
- Dubai Land Department (DLD) fiscaliza e audita regularmente
- Banco retém 5% até 1 ano após registro das unidades (incentivo legal para registro)
- Proteção automática do comprador: reembolso ou conclusão do projeto em caso de falha

**Implicação Prática:**
- Compradores off-plan nos EAU têm proteção legal automática
- Documentos de pagamento via Payment Agent + Supplementary Agreement são suficientes
- Não é necessário comprovante adicional do repasse para Escrow Account (desenvolvedor é obrigado por lei a fazer o depósito)

---

### Pendências e próximos passos

#### 1. Apresentação Premium Cliente Fábio
- **Status:** Funcional, mas pode necessitar de ajustes finos nas imagens ou texto.
- **Ação:** Aguardar feedback do cliente para possíveis refinamentos.

#### 2. Verificação de Mobília DAMAC Valencia
- **Questão:** Cliente perguntou se os Studios do DAMAC Valencia vêm mobiliados.
- **Resposta:** Os documentos fornecidos (Onepager e Factsheet) **não mencionam** mobília. Geralmente, projetos DAMAC Lagoons são entregues com acabamento básico (cozinha equipada), mas sem mobília solta.
- **Ação:** Confirmar diretamente com a DAMAC se há oferta de "fully furnished" para o Valencia.

#### 3. Documentação de Processos
- **Regra de EOI abatida:** Documentada e estabelecida como padrão.
- **Planos de pagamento por desenvolvedor:** Documentados (Object-1, DAMAC, EMAAR).
- **Ação:** Manter esses padrões atualizados conforme novos projetos forem analisados.

#### 4. Material do Grupo Ark
- **Contexto:** Projeto original era criar apresentação institucional do Ark Group.
- **Status:** Pausado para priorizar apresentações imobiliárias urgentes.
- **Ação:** Retomar quando houver todas as informações e orientações finalizadas (conforme instrução inicial do projeto).

---

### Arquivos e artefatos

#### Apresentações Finais (Nano Banana Slides)
1. **Radisson Blu RAK + Orvessa Residences:**
   - Diretório: `/home/ubuntu/Presentacion_Radisson_Orvessa_ES`
   - Link: `manus-slides://oL7gnuxllonJY9avJfgz3f`
   - Idioma: Espanhol
   - Slides: 16

2. **Cliente Amador (Object-1 + DAMAC Valencia):**
   - Diretório: `/home/ubuntu/Presentacion_Cliente_Amador_ES`
   - Link: `manus-slides://oL7gnuxllonJY9avJfgz3f`
   - Idioma: Espanhol
   - Slides: 16

3. **Cliente Fábio Premium (DAMAC Islands 2 + The Valley Amelia):**
   - Diretório: `/home/ubuntu/Presentacion_Premium_Fabio_ES_V2`
   - Link: `manus-slides://4tOv2TrNqLAgWQilbmIVva`
   - Idioma: Espanhol
   - Slides: 16

#### Arquivos de Dados e Análises
1. **Análises Financeiras:**
   - `/home/ubuntu/Radisson_Orvessa_Financial_Analysis.txt`
   - `/home/ubuntu/Radisson_Orvessa_Financial_Analysis_3_Currencies.txt`
   - `/home/ubuntu/Premium_Projects_Financial_Data.txt`

2. **Dados dos Projetos:**
   - `/home/ubuntu/Alta_View_Elaris_Sky_Data.txt`
   - `/home/ubuntu/Orvessa_Project_Data.md`
   - `/home/ubuntu/DAMAC_Islands2_Premium_Data.txt`
   - `/home/ubuntu/The_Valley_Amelia_Premium_Data.txt`
   - `/home/ubuntu/New_Options_Data.txt`

3. **Análise Legal:**
   - `/home/ubuntu/analise_pagamento_fabio_celestino.txt`
   - `/home/ubuntu/dubai_escrow_law_key_findings.txt`

4. **Outlines e Planejamento:**
   - `/home/ubuntu/Outline_Presentacion_Radisson_Orvessa_ES.md`
   - `/home/ubuntu/Outline_Premium_Fabio_ES.md`

#### PDFs Recebidos (Brochuras e Sales Offers)
- **Object-1:**
  - `ALTAV1EWSKYHOMES_1_5_1BR_Type12_509_735.93_Feb09,2026.pdf`
  - `ELAR1SSKY_1_11_1BR_Type19_1104_720.62_Feb09,2026.pdf`

- **DAMAC Valencia:**
  - `P&V_Onepager_29_1_26.pdf`
  - `FACTSHEETV&P.pdf`

- **DAMAC Islands 2:**
  - `DAMACISLANDS2Brochure_DIGITAL_ENG_NOV12.pdf`
  - `DIBS2_SD129_G003X10.pdf` (Studio)
  - `DIBR1_SD212_B087X07.pdf` (Villa 4BR Barbados)

- **The Valley Amelia:**
  - `AVELIA_TV_BROCHURE.pdf`
  - `TVAvelia-V-132EmaarSalesOffer--1770622735212.pdf` (Villa 5BR)
  - `TVAvelia-V-13EmaarSalesOffer--1770622697309.pdf` (Villa 4BR)

- **Análise Legal:**
  - `20260209173513.pdf` (Supplementary Agreement)
  - `Выписка_40807810314900000166_от_05_01_2026_05_02_2026.pdf` (Extrato Bancário Russo)

#### Scripts Python Utilizados
- `/home/ubuntu/calc_amador_financial.py` (Análise financeira Cliente Amador)
- `/home/ubuntu/calc_payment_tables.py` (Tabelas de pagamento detalhadas)
- `/home/ubuntu/calc_valencia_15pct.py` (DAMAC Valencia com 15% entrada)
- `/home/ubuntu/calc_valencia_60_40.py` (DAMAC Valencia plano 60/40 com EOI abatida)

---

### Referências Legais

1. **Dubai Law No. 8 of 2007 Concerning Escrow Accounts for Real Estate Development in the Emirate of Dubai**  
   URL: https://dlp.dubai.gov.ae/Legislation%20Reference/2007/Law%20No.%20(8)%20of%202007.html

2. **Developer Compliance in Off-Plan Projects - BSA LAW**  
   URL: https://bsalaw.com/insight/navigating-dubais-off-plan-real-estate-laws-compliance-essentials-for-developers/

3. **How the UAE escrow law protects off-plan property buyers - Knightsbridge**  
   URL: https://knightsbridge.ae/how-the-uae-escrow-law-protects-off-plan-property-buyers/

---

**Autor:** Manus AI  
**Projeto:** Ark Group - Apresentações Imobiliárias e Consultoria Legal  
**Data de Documentação:** 10 de Fevereiro de 2026

---

## 6. Estruturação Fiscal e Patrimonial de Holding Internacional para Fabio Celestini

**Data:** Fevereiro 2026
**Status:** Concluída
**Projeto relacionado:** Ark Group (Lap5wRprqDR5x9DiXU3WBL)

### O que foi feito

Desenvolveu-se análise estratégica completa para estruturação de holding internacional visando otimização fiscal e proteção patrimonial de 4 propriedades residenciais em Miami (aluguel bruto USD 10.650/mês, despesas locais USD 5.270/mês, lucro operacional USD 5.380/mês).

**Análises Realizadas:**

1. **Mapeamento de Cenários** - Comparação entre 3 estruturas:
   - Pessoa Física Não-Residente (status atual): USD 5.380/mês, sem tributação federal EUA, mas sem proteção patrimonial
   - Delaware LLC (C-Corp): USD 4.197,82/mês (tributação 21% federal + 5,5% Florida = USD 1.182,18/mês), com proteção patrimonial e blindagem legal
   - Delaware + Holanda BV: Redução de WHT de 30% para 5% em distribuições, com custos operacionais adicionais USD 1.000-1.500/mês

2. **Validação de Hipóteses** - Pesquisa técnica com IA especializada confirmou:
   - USD 24.247/ano em Property Tax (não tributação federal) continua igual em qualquer estrutura
   - Tributação sobre lucro é o único elemento variável
   - Tratado EUA-Rússia suspenso em agosto 2024 (impacto na estratégia de distribuição)
   - Rússia não é territorial para pessoas físicas residentes (13-22% sobre renda mundial)

3. **Identificação de Alternativas de Otimização:**
   - Opção 1: Dividir 4 propriedades em 2 LLCs (USD 2.690/mês cada) para ficar abaixo de USD 50k/ano e eliminar tributação federal (economia USD 1.182/mês, mas custos administrativos duplicam)
   - Opção 2: Colocar 2 propriedades em nome da esposa (diversificação de risco, sem economia tributária)
   - Opção 3: Reter lucros na LLC (USD 0/mês distribuído, crescimento composto USD 50.373,84/ano)
   - Opção 4: Adicionar Holanda BV para reduzir WHT em distribuições

4. **Documentação Gerada:**
   - Análise técnica detalhada com cálculos de tributação por jurisdição
   - Documento executivo em espanhol com introdução sobre benefícios da holding
   - Resposta conversacional em português (tom natural, não robótico) para apresentação ao cliente
   - Comparação lado a lado de todos os cenários com valores exatos

**Decisões Implementadas:**
- Recomendação de Delaware LLC (C-Corp) como estrutura base (melhor balanço entre proteção e custo)
- Enfoque em proteção patrimonial como prioridade sobre maximização de caixa imediato
- Estrutura em fases: Fase 1 (implementação Delaware agora), Fase 2 (otimizações futuras)
- Abordagem consultiva: apresentar alternativas sem forçar decisão, deixar cliente escolher prioridade

### Decisões técnicas relevantes

1. **Estrutura de Holding em Cascata vs. Paralela:**
   - Inicialmente explorou-se cascata (LLC → Holanda → ADGM)
   - Pivotou para paralela (Delaware LLC + Holanda BV, ambas sob ADGM Foundation) após feedback do cliente
   - Holanda BV justificada apenas se houver propriedades europeias (não é caso atual)

2. **Eleição de Tributação (Form 8832):**
   - Delaware LLC eleita como C-Corporation (não Disregarded Entity)
   - Razão: Evita risco de "Branch Profits Tax" (BPT) de 30% e oferece maior flexibilidade de reinvestimento
   - C-Corp permite retenção de lucros sem distribuição imediata

3. **Tratamento de Property Tax:**
   - Confirmado que USD 24.247/ano é imposto local (ad valorem + non-ad valorem)
   - Continua igual em qualquer estrutura (pessoa física ou LLC)
   - Não deve ser incluído em cálculos de tributação federal

4. **Critério de USD 50k/ano:**
   - Pesquisa confirmou que lucro operacional abaixo de USD 50k/ano em LLC pode qualificar para isenções específicas
   - Aplicável apenas se dividir em múltiplas LLCs (não é automático)
   - Trade-off: economia tributária vs. custos administrativos duplicados

5. **Abordagem de Distribuição vs. Retenção:**
   - Retenção de lucros na LLC oferece crescimento composto sem WHT (USD 503.738 em 10 anos)
   - Distribuição com Holanda BV reduz WHT de 30% para 5% (economia USD 12.591/ano)
   - Cliente deve decidir prioridade: liquidez imediata vs. crescimento patrimonial

6. **Documentação para Conformidade:**
   - W-8BEN-E obrigatório para manter status não-residente (cliente deve confirmar se tem)
   - CRS/FATCA compliance obrigatório (Rússia é membro)
   - Atas de reuniões e documentação de substância essencial para defender estrutura

### Pendências e próximos passos

1. **Confirmações Necessárias com Fabio:**
   - Status atual do W-8BEN-E (tem certificado válido?)
   - Tributação pessoal na Rússia (é residente fiscal? Quanto paga?)
   - Prioridade: caixa máximo vs. proteção vs. crescimento?
   - Intenção com propriedades: manter, vender, expandir?

2. **Implementação (se aprovado):**
   - Constituição Delaware LLC (C-Corp) - USD 90-110 + documentação
   - Form 8832 election (C-Corp) - USD 0 (eleição interna)
   - Documentary Stamp Tax (Florida) - USD 1.500-3.000
   - Transferência de propriedades para LLC (4 atos de transferência)
   - Contabilidade anual (USD 2.000-4.000/ano)
   - Timeline: 4-6 semanas para implementação completa

3. **Otimizações Futuras (Fase 2):**
   - Avaliar divisão em 2 LLCs se economia tributária justificar custos
   - Adicionar Holanda BV se cliente decidir distribuir lucros regularmente
   - Explorar estrutura com esposa (diversificação de risco)
   - Avaliar reinvestimento em propriedade 5 (crescimento escalado)

4. **Riscos Residuais:**
   - LOB (Limitation of Benefits) - mitigado com C-Corp, mas requer documentação robusta
   - IRS challenge ao status não-residente - mitigado com W-8BEN-E válido
   - Mudança legislativa (EUA, Rússia, Emirados) - monitorar anualmente
   - Estate Tax (40% sobre valor acima USD 60k) - mitigado com estrutura, mas requer ILIT para máxima proteção

5. **Questões Abertas:**
   - Holanda BV é necessária? (Apenas se houver propriedades europeias)
   - Cenário 3 (Holanda com distribuição) será explorado em fase posterior?
   - Qual é a estrutura ideal para sucessão (ILIT, Trust, Fundação ADGM)?

### Arquivos e artefatos

**Documentos Principais Gerados:**

1. `/home/ubuntu/DOCUMENTO_FABIO_ESPANHOL_FINAL.md` - Documento executivo em espanhol (FINAL, pronto para envio)
   - Introdução sobre benefícios da holding
   - Comparação Hoje vs. Com Delaware
   - 3 alternativas de otimização
   - Tabela comparativa
   - Valores exatos (USD 5.380 → USD 4.197,82/mês)

2. `/home/ubuntu/RESPOSTA_CONVERSACIONAL_FABIO.md` - Resposta em português (tom conversacional)
   - Explicação natural do cenário
   - Menção de possibilidades sem detalhar todas
   - Convite para revisar documento

3. `/home/ubuntu/ANALISE_COMPLETA_CALCULOS_REAIS_FABIO.md` - Análise técnica detalhada
   - Cálculos completos com valores exatos
   - Comparação de 5 cenários
   - Análise de futuro (venda, distribuição, sucessão)

4. `/home/ubuntu/ESTRATEGIA_FINAL_EMPRESTIMO_SOCIO.md` - Estratégia avançada (empréstimo ao sócio)
   - Retenção de lucros + empréstimo para Fabio
   - Crescimento composto sem tributação
   - Fluxo de caixa mantido (USD 3.837/mês)

5. `/home/ubuntu/PARECER_REVISADO_ESTRUTURA_PARALELA.md` - Análise de estrutura em paralelo
   - Delaware LLC + Holanda BV (ambas sob ADGM)
   - Comparação de custos e tributação
   - Análise de riscos (LOB, ATAD2, Estate Tax)

6. `/home/ubuntu/ANALISE_RISCOS_REAIS_E_ALTERNATIVAS_OTIMIZADAS.md` - Mapeamento de riscos
   - 7 riscos identificados com probabilidade e impacto
   - Risco total acumulado: USD 614.773-1.453.866
   - Mitigações por risco

7. Prompts para IA (Raciel):
   - `/home/ubuntu/PROMPT_PESQUISA_ALTERNATIVAS_FISCAIS_OTIMIZADAS.txt`
   - `/home/ubuntu/PROMPT_OPCO_HOLDCO_LEVERAGE.txt`
   - `/home/ubuntu/PROMPT_CENARIOS_ALTERNATIVOS_VALORES_EXATOS.txt`
   - `/home/ubuntu/PROMPT_FINAL_DELAWARE_CUSTOS_OTIMIZACOES.txt`

**Documentos de Análise Intermediária (Referência):**
- HAZELANALYSIS_Celestini11.02.2026.docx (documento técnico original em inglês)
- PARECER_EXECUTIVO_ESTRUTURA_INTERNACIONAL_PT.md
- ANALISE_FINANCEIRA_FABIO_NUMEROS_REAIS.md

**Fluxo de Trabalho:**
1. Análise HAZELANALYSIS (documento técnico em inglês) → validação com IA
2. Pesquisa de legislação (2026) → confirmação de status de tratados
3. Cálculos com valores exatos → comparação de cenários
4. Identificação de alternativas → avaliação de trade-offs
5. Documentação executiva → apresentação ao cliente

**Tecnologias/Ferramentas Utilizadas:**
- MCP (Model Context Protocol) - Integração com IA especializada (Raciel)
- Markdown para documentação estruturada
- Cálculos financeiros (Python/Excel simulado)
- Pesquisa de legislação fiscal (IRC, tratados, CRS/FATCA)

**Status de Cada Documento:**
- ✅ DOCUMENTO_FABIO_ESPANHOL_FINAL.md - PRONTO PARA ENVIO
- ✅ RESPOSTA_CONVERSACIONAL_FABIO.md - PRONTO PARA ENVIO
- ✅ Análises técnicas - COMPLETAS (referência)
- ⏳ Implementação - AGUARDANDO APROVAÇÃO DO CLIENTE

---

## Observações Finais

- Fluxo de trabalho estabelecido: Análise → Validação → Ajuste → Documento Final
- Cliente (você) atua como intermediário entre análise técnica e cliente final (Fabio)
- Abordagem consultiva: apresentar alternativas, deixar cliente decidir
- Próxima fase depende de aprovação de Fabio e confirmação de informações pendentes

---

## 7. Framework Contratual ARK Group v2.0 com Design System Corporativo

**Data:** 12-13 de fevereiro de 2026  
**Status:** Concluída  
**Projeto relacionado:** Ark Group (Lap5wRprqDR5x9DiXU3WBL)

---

## O que foi feito

Criação completa de um framework contratual world-class para a ARK Group, incorporando melhorias dos templates da Hazel e desenvolvendo um design system visual corporativo profissional.

### Fase 1 - Análise e Planejamento

- Análise comparativa entre framework v1.0 existente e templates da Hazel
- Identificação de 5 categorias de melhorias: proteção legal, governança, compliance, novos documentos e clareza operacional
- Documento gerado: `Analise_Comparativa_Templates_Hazel.pdf`

### Fase 2 - Desenvolvimento do Framework v2.0

Criados 7 documentos contratuais em Markdown com melhorias incorporadas:

#### 1. Master Services & Collaboration Agreement (MSCA) v2.0
Contrato-mãe com:
- Vigência com renovação automática (36 meses + 12 meses)
- Quorum qualificado para decisões críticas (>USD 5M, cripto, exclusividades)
- Cláusula de IP (propriedade intelectual e know-how)
- Proteção de dados (LGPD/GDPR, SCCs, clean team)
- Limite de responsabilidade (12x fee ou 2% do sucesso)
- Estrutura de 3 partes: Marcos/ARK SPV + Terra Brasilis + Brazil Investments

#### 2. Statement of Work (SOW) Template v2.0
Template para projetos específicos com:
- Critérios de aceite para entregáveis
- Exemplo numérico vinculante
- Condições suspensivas
- Compliance específico (cripto/OTC, setor público)

#### 3. Deal Participation Agreement (DPA) Template v2.0
Para comissionamento com terceiros:
- Split de comissões com percentuais claros
- Gatilho de pagamento (Signing/Closing/Funding)
- Back-to-back com SOW

#### 4. Joinder Agreement Template v2.0
Para adesão de novos stakeholders:
- Reconhecimento da Novação PF → ARK
- Representações de Compliance

#### 5. Side Letter - Compliance & Confidentiality v2.0
Para projetos sensíveis:
- Classificação de dados (4 níveis)
- Clean Team e acesso restrito
- Travel Rule, KYT, whitelist de carteiras
- Sanctions screening periódico

#### 6. Payment Instructions Letter v2.0
Instruções para Escrow/Paymaster:
- Evento gatilho e documentação
- Ordem de pagamentos (Waterfall)
- Procedimento em disputas

#### 7. Anexo A - Waterfall de Pagamentos v2.0
Ordem de distribuição de fundos em 4 passos

### Fase 3 - Design System Corporativo

Desenvolvido sistema de identidade visual completo:

#### Paleta de cores
- **ARK Navy:** `#1A2332` (títulos)
- **ARK Gold:** `#C9A961` (destaques)
- **ARK Slate:** `#4A5568` (subtítulos)
- **Texto principal:** `#2D3748`
- **Background alternativo:** `#F7FAFC`

#### Tipografia
- **Fonte:** Inter (Google Fonts)
- **Hierarquia:** Bold 24pt (títulos) → Regular 14pt (subtítulos) → SemiBold 14pt (cláusulas) → Regular 11pt (corpo)
- **Line-height:** 1.6 (corpo), 1.3 (títulos)

#### Layout
- **Margens:** 30mm (esquerda), 25mm (demais)
- **Alinhamento:** esquerda (títulos e cláusulas), justificado (corpo)
- **Controle de quebra de página:** `page-break-inside: avoid` em tabelas e assinaturas

### Fase 4 - Automação

- Script Python `apply_template.py`: converte Markdown → HTML com template ARK
- Template HTML/CSS: `ark_contract_template_v2.html` (versão corrigida após feedback)
- Conversão HTML → PDF via WeasyPrint

### Fase 5 - Documentação

- `Guia_Pratico_Documentos_v2.pdf`: manual explicativo de quando usar cada documento com exemplos práticos, checklists por tipo de projeto e FAQs
- `ARK_Contract_Design_System.pdf`: especificações completas do design system

---

## Decisões técnicas relevantes

### Estrutura de 3 partes mantida

Optou-se por manter a estrutura de 3 partes (Marcos/ARK + Terra Brasilis + Brazil Investments) do framework v1.0, que é superior ao template da Hazel (2 partes), incorporando apenas as melhorias técnicas.

### Markdown como fonte, HTML+CSS como template

- Conteúdo em Markdown puro (editável, versionável)
- Template visual em HTML/CSS separado (reutilizável)
- Conversão automatizada via script Python
- PDF final via WeasyPrint (melhor controle de layout que manus-md-to-pdf)

### Correção crítica de formatação

Após feedback do usuário, o template foi completamente refatorado:
- **v1 (rejeitada):** Títulos centralizados, layout "web-like"
- **v2 (aprovada):** Títulos à esquerda, texto justificado, formato de documento legal tradicional

### Trade-offs

- WeasyPrint não suporta `calc()` em CSS (`width: calc(210mm - 55mm)`) → warnings ignorados, não afetam output
- Rodapé via CSS `@page @bottom-center` não renderiza corretamente no WeasyPrint → removido da versão final
- Controle de quebra de página via `page-break-inside: avoid` funciona bem para tabelas e assinaturas

### Compliance e jurisdição

- **Lei aplicável:** DIFC (Dubai International Financial Centre)
- **Arbitragem:** DIAC (Dubai International Arbitration Centre)
- **Proteção de dados:** LGPD (Brasil) + GDPR (EU) via SCCs

---

## Pendências e próximos passos

### Skill "ark-contracts" (iniciada, não concluída)

- Diretório criado: `/home/ubuntu/skills/ark-contracts/`
- Scripts copiados: `apply_template.py`
- Templates copiados: `ark_contract_template_v2.html`
- References copiados: todos os 7 templates .md + `design_system.md`
- **PENDENTE:** Escrever `SKILL.md` completo com frontmatter e instruções
- **PENDENTE:** Validar skill com `quick_validate.py`
- **PENDENTE:** Entregar skill ao usuário

### Melhorias futuras identificadas

1. Adicionar logo da ARK ao cabeçalho dos PDFs (atualmente placeholder)
2. Implementar numeração de páginas funcional no rodapé
3. Criar versões em inglês dos 7 documentos
4. Desenvolver SOWs específicos para projetos prioritários:
   - SOW-003: Floridian Monaco (com DPA e Payment Instructions)
   - SOW-004: Porto Litoral Norte (com DPA)
   - SOW-002: Stratum Brazil (híbrido retainer + equity)

### Informações corporativas pendentes

Para finalizar o MSCA, necessário coletar:
- **Terra Brasilis:** jurisdição, nº registro, endereço sede, representante legal
- **Brazil Investments:** jurisdição, nº registro, endereço sede, representante legal

---

## Arquivos e artefatos

### Documentos contratuais finais (PDF com design ARK)

- `/home/ubuntu/Master_Services_Collaboration_Agreement_v2_final.pdf` (48KB)
- `/home/ubuntu/Statement_of_Work_Template_v2_final.pdf` (50KB)
- `/home/ubuntu/Deal_Participation_Agreement_Template_v2_final.pdf` (39KB)
- `/home/ubuntu/Joinder_Agreement_Template_v2_final.pdf` (29KB)
- `/home/ubuntu/Side_Letter_Compliance_Template_v2_final.pdf` (37KB)
- `/home/ubuntu/Payment_Instructions_Letter_Template_v2_final.pdf` (36KB)
- `/home/ubuntu/Anexo_A_Waterfall_Template_v2_final.pdf` (29KB)

### Documentos fonte (Markdown)

- `/home/ubuntu/Master_Services_Collaboration_Agreement_v2.md`
- `/home/ubuntu/Statement_of_Work_Template_v2.md`
- `/home/ubuntu/Deal_Participation_Agreement_Template_v2.md`
- `/home/ubuntu/Joinder_Agreement_Template_v2.md`
- `/home/ubuntu/Side_Letter_Compliance_Template_v2.md`
- `/home/ubuntu/Payment_Instructions_Letter_Template_v2.md`
- `/home/ubuntu/Anexo_A_Waterfall_Template_v2.md`

### Documentação

- `/home/ubuntu/Guia_Pratico_Documentos_v2.pdf` - Manual de uso dos documentos
- `/home/ubuntu/ARK_Contract_Design_System.pdf` - Especificações do design system
- `/home/ubuntu/Analise_Comparativa_Templates_Hazel.pdf` - Análise das melhorias

### Infraestrutura técnica

- `/home/ubuntu/ark_contract_template_v2.html` - Template HTML/CSS final (corrigido)
- `/home/ubuntu/apply_template.py` - Script de conversão Markdown → HTML
- `/home/ubuntu/skills/ark-contracts/` - Diretório da skill (incompleto)

### Versões anteriores (descontinuadas)

- `*_v1.pdf` - Versão inicial sem melhorias da Hazel
- `*_styled.pdf` - Versão com formatação centralizada (rejeitada)

### Matriz de controle

- `/home/ubuntu/Project_Control_Matrix.xlsx` - Planilha de controle de 7 projetos (SOW-001 a SOW-007)

### Tecnologias utilizadas

- Python 3.11 + markdown library
- WeasyPrint para conversão HTML → PDF
- Google Fonts (Inter)
- CSS3 com @page rules

---

## 8. Configuração Completa de Email Profissional e Google Workspace para arkstrategy.ae

**Data:** 13 de fevereiro de 2026  
**Status:** Concluída  
**Projeto relacionado:** ARK GROUP Command Center (CRM)

---

## O que foi feito

### 1. Aquisição e Configuração de Domínio

- **Domínio adquirido:** arkstrategy.ae
- **Registrador:** AEServer (https://my.aeserver.com)
- **Custo:** AED 136.50/ano
- **Nameservers:** dns1.aeserver.com, dns2.aeserver.com, dns3.aeserver.com
- **Status:** Ativo desde 13/02/2026
- **Renovação:** Auto-renovação ativada (próxima renovação: 13/02/2027)

### 2. Contratação Google Workspace

- **Plano selecionado:** Business Standard
- **Custo:** USD 16.80/mês (AED ~61.70/mês)
- **Recursos incluídos:**
  - 2TB de armazenamento por usuário
  - Gmail profissional com domínio personalizado
  - Google Meet (até 150 participantes)
  - Google Drive, Docs, Sheets, Slides
  - Google Calendar
  - Suporte 24/7

### 3. Criação de Usuário

- **Email criado:** marcos@arkstrategy.ae
- **Tipo:** Administrador (owner)
- **Senha:** Configurada pelo usuário
- **Pergunta de segurança:** "montecarmelo" ou "monte carmelo"

### 4. Verificação de Domínio (DNS TXT Record)

**Registro adicionado no AEServer DNS Management:**

```
Type: TXT
Hostname: @
Value: google-site-verification=jcqsykY2tvVclCU5HlOn5iS2g49zt13KLCvMLPaiiBI
TTL: 3600
```

**Status:** ✅ Verificado com sucesso  
**Resultado:** "Your domain is verified!" - Domínio arkstrategy.ae verificado e pronto para usar Google Workspace apps

### 5. Ativação do Gmail (MX Record)

**Registro adicionado no AEServer DNS Management:**

```
Type: MX
Hostname: @
Priority: 1
Address: SMTP.GOOGLE.COM
TTL: 3600
```

**Status:** ✅ Gmail ativado com sucesso  
**Resultado:** "Gmail is activated!" - Emails @arkstrategy.ae agora são direcionados para Gmail  
**Propagação:** Pode levar até 24 horas para propagação completa do DNS

### 6. Configuração DKIM (Autenticação de Email)

**Registro adicionado no AEServer DNS Management:**

```
Type: TXT
Hostname: google._domainkey
Value: v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAGrSF2S5KHPqJ2Slj8g70f50Zu2djXxIlVmp7fIVbF33Ghmwuk70wrIYowkWaud9dT2ZQgm0hx0qBPdzjlQCYL1YhFYch5r1pW3VQlDAQAB
TTL: 3600
```

**Status:** ✅ DKIM configurado  
**Benefícios:**
- Autenticação digital de emails enviados
- Redução de chance de emails caírem em spam
- Maior confiabilidade para emails corporativos
- Compliance com padrões de segurança de email

### 7. Configuração no Cliente de Email

- **Cliente:** Mail (aplicativo nativo do macOS)
- **Conta adicionada:** marcos@arkstrategy.ae
- **Método:** Integração Google (OAuth)
- **Sincronização ativada:**
  - ✅ Mail (emails)
  - ✅ Contacts (contatos)
  - ✅ Calendars (calendários Google)
  - ✅ Notes (notas)

### 8. Personalização do Workspace

**Wizard de setup completado (3 etapas):**

1. **Primeira ação escolhida:** Send emails (ir direto para Gmail)
2. **Objetivos selecionados:**
   - Connect with customers
   - Collaborate with my team
   - Improve my productivity
3. **Apps familiares indicados:**
   - Gmail
   - Google Calendar
   - Google Drive

---

## Decisões técnicas relevantes

### 1. Escolha do Domínio .ae

**Decisão:** Optar por .ae (Emirados Árabes) ao invés de .com ou .org

**Justificativa:**
- Empresa opera em Dubai, UAE
- Domínio .ae transmite localização e credibilidade regional
- Custo: AED 136.50/ano (mais caro que .org mas mais relevante)

### 2. Plano Google Workspace Business Standard

**Decisão:** Business Standard (USD 16.80/mês) ao invés de Business Starter (USD 6/mês)

**Trade-offs analisados:**
- Business Starter: 30GB por usuário
- Business Standard: 2TB por usuário (66x mais espaço)
- Diferença de custo: +USD 10.80/mês
- **Justificativa:** Armazenamento de propostas, documentos, gravações de reuniões justifica o investimento

### 3. Configuração DNS via AEServer

**Decisão:** Gerenciar DNS diretamente no AEServer ao invés de migrar para Cloudflare ou Google Domains

**Justificativa:**
- Domínio .ae tem restrições de transferência
- AEServer é registrador oficial .ae
- DNS Management disponível no painel AEServer
- Evita complexidade de múltiplos provedores

### 4. DKIM com Chave 2048-bit

**Decisão:** Usar chave DKIM de 2048 bits (padrão Google)

**Alternativa considerada:** 1024-bit (mais compatível com hosts antigos)

**Justificativa:**
- Google recomenda 2048-bit para segurança
- AEServer suporta chaves longas
- Maior segurança para emails corporativos

### 5. Cliente de Email: Mail (macOS) ao invés de Gmail Web

**Decisão:** Configurar no app Mail nativo do Mac

**Justificativa do usuário:**
- Preferência por app nativo
- Facilidade de alternar entre contas (pessoal + profissional)
- Integração com sistema operacional
- Notificações nativas

---

## Pendências e próximos passos

### 1. Propagação DNS Completa

**Status:** Em andamento (pode levar até 24-48h)

**Ação requerida:** Aguardar propagação completa dos registros MX

**Como verificar:**
```bash
# Verificar MX record
dig arkstrategy.ae MX

# Verificar TXT records
dig arkstrategy.ae TXT

# Verificar DKIM
dig google._domainkey.arkstrategy.ae TXT
```

**Teste de email:** Enviar email de teste de marcos@arkstrategy.ae para email externo e verificar recebimento

### 2. Configuração SPF (Sender Policy Framework)

**Status:** Não configurado

**Recomendação:** Adicionar registro SPF para aumentar deliverability

**Registro sugerido:**
```
Type: TXT
Hostname: @
Value: v=spf1 include:_spf.google.com ~all
TTL: 3600
```

**Benefício:** Previne spoofing e melhora reputação do domínio

### 3. Configuração DMARC

**Status:** Não configurado

**Recomendação:** Adicionar política DMARC para monitoramento

**Registro sugerido:**
```
Type: TXT
Hostname: _dmarc
Value: v=DMARC1; p=none; rua=mailto:marcos@arkstrategy.ae
TTL: 3600
```

**Benefício:** Receber relatórios de autenticação de email e proteger contra phishing

### 4. Integração com ARK GROUP Command Center

**Status:** Não iniciado

**Possibilidades:**

a) **Templates de Email no CRM:**
   - Criar biblioteca de templates profissionais
   - Modelos para propostas, follow-ups, agradecimentos
   - Integração com dados de clientes/deals

b) **Registro de Comunicações:**
   - Adicionar campo "Email enviado" nas atividades
   - Histórico de comunicação por cliente
   - Timeline de interações

c) **Gmail API Integration (Avançado):**
   - Requer OAuth setup
   - Sincronização automática de emails com CRM
   - Leitura/envio programático de emails
   - **Trade-off:** Complexidade técnica vs automação

### 5. Configuração de Assinatura de Email

**Status:** Não configurado

**Próximo passo:** Criar assinatura profissional no Gmail

**Elementos sugeridos:**
```
---
Marcos [Sobrenome]
Founder & CEO | ARK Strategy

📧 marcos@arkstrategy.ae
📱 +971 52 362 0109
🌐 arkstrategy.ae
📍 Dubai, UAE

[Logo ARK Strategy]
```

### 6. Backup e Segurança

**Recomendações pendentes:**

a) **2FA (Two-Factor Authentication):**
   - Ativar autenticação de dois fatores na conta Google Workspace
   - Aumenta segurança contra acesso não autorizado

b) **Backup de Emails:**
   - Google Vault (disponível no Business Standard)
   - Retenção e arquivamento de emails
   - Compliance e auditoria

c) **Políticas de Senha:**
   - Definir política de troca de senha periódica
   - Requisitos de complexidade

### 7. Adicionar Usuários Futuros

**Status:** Apenas 1 usuário (marcos@arkstrategy.ae)

**Quando adicionar equipe:**
- Custo: USD 16.80/mês por usuário adicional
- Processo: Admin Console → Users → Add new user
- Emails sugeridos: team@arkstrategy.ae, contact@arkstrategy.ae, etc.

### 8. Configurar Aliases de Email

**Status:** Não configurado

**Sugestões de aliases para marcos@arkstrategy.ae:**
- contact@arkstrategy.ae
- info@arkstrategy.ae
- ceo@arkstrategy.ae

**Benefício:** Múltiplos endereços apontando para mesma caixa de entrada (sem custo adicional)

### 9. Website Institucional para arkstrategy.ae

**Status:** Não iniciado (mencionado pelo usuário)

**Contexto:** Domínio atualmente mostra página de "parking" do AEServer

**Próximos passos:**
- Definir escopo do site institucional
- Escolher plataforma (Manus web-static, WordPress, etc.)
- Criar conteúdo (sobre, serviços, contato)
- Design e desenvolvimento
- Deploy e apontamento DNS (A record)

---

## Arquivos e artefatos

### 1. Credenciais e Acessos

**AEServer (Registrador de Domínio):**
- URL: https://my.aeserver.com/clientarea.php
- Domínio: arkstrategy.ae
- ID do domínio: 119568
- DNS Management: my.aeserver.com/?m=cnicdnsmanager&domainid=119568

**Google Workspace Admin Console:**
- URL: https://admin.google.com
- Email admin: marcos@arkstrategy.ae
- Organização: Ark Strategy

**Gmail:**
- URL: https://mail.google.com
- Email: marcos@arkstrategy.ae

### 2. Registros DNS Configurados

**Resumo completo dos registros DNS em arkstrategy.ae:**

```dns
# A Record (IP do servidor)
@    3600    A    165.22.30.248

# CNAME (www)
www    3600    CNAME    arkstrategy.ae

# MX Record (Email)
@    3600    MX    1    SMTP.GOOGLE.COM

# TXT Record (Verificação de Domínio)
@    3600    TXT    "google-site-verification=jcqsykY2tvVclCU5HlOn5iS2g49zt13KLCvMLPaiiBI"

# TXT Record (DKIM - Autenticação de Email)
google._domainkey    3600    TXT    "v=DKIM1; k=rsa; p=MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAGrSF2S5KHPqJ2Slj8g70f50Zu2djXxIlVmp7fIVbF33Ghmwuk70wrIYowkWaud9dT2ZQgm0hx0qBPdzjlQCYL1YhFYch5r1pW3VQlDAQAB"
```

### 3. Documentação de Referência

**Guias Google Workspace utilizados:**
- Domain verification: workspace.google.com/u/2/getsetup/domain/verification/confirmation
- Gmail activation: workspace.google.com/u/2/verify/activategmail/codes
- DKIM setup: workspace.google.com/u/2/getsetup/domain/dkim/codes

**Ferramentas de Verificação DNS:**
- Google Admin Toolbox: https://toolbox.googleapps.com/apps/checkmx/
- MXToolbox: https://mxtoolbox.com/SuperTool.aspx?action=mx%3aarkstrategy.ae
- WhatsMyDNS: https://www.whatsmydns.net/#MX/arkstrategy.ae

### 4. Custos Recorrentes

**Resumo financeiro:**

| Item | Custo | Frequência | Anual |
|------|-------|------------|-------|
| Domínio arkstrategy.ae | AED 136.50 | Anual | AED 136.50 |
| Google Workspace Business Standard | USD 16.80 | Mensal | USD 201.60 |
| **Total anual estimado** | | | **~USD 238 + AED 137** |

**Conversão aproximada (1 USD = 3.67 AED):**
- Total anual: ~AED 1.010

### 5. Contexto do Projeto ARK GROUP

**Relação com Command Center CRM:**
- Email profissional para comunicação com clientes do pipeline
- 21 deals ativos no CRM (USD 42.4M)
- Integração futura: envio de propostas, follow-ups, lembretes

**Clientes principais no pipeline:**
- Denise (Holding - USD 10.5k)
- Nexus/Diego Alves (USD 20k)
- José Blesa (CSKA - Holding + Apartamento - USD 555.5k)
- Eduardo Malheiros (Investimento Ark.Technology - USD 250k)
- Liliane Garmes (Expansão Dubai - USD 2.35k)
- YAÍ (Expansão Dubai - USD 3.825k)

**Contato do usuário:**
- WhatsApp: +971 52 362 0109
- Email pessoal: marcos.arkuae@gmail.com
- Email profissional: marcos@arkstrategy.ae
- Localização: Dubai, UAE (GMT+4)

---

## Notas técnicas adicionais

### Troubleshooting Realizado

**Problema 1:** Usuário clicou em "Confirm" antes de adicionar MX record
- **Solução:** Voltou, adicionou MX record, aguardou verificação
- **Resultado:** Verificação bem-sucedida após adição correta

**Problema 2:** Confusão sobre onde adicionar DNS records
- **Solução:** Navegação guiada: Domains → arkstrategy.ae → DNS Management
- **Interface AEServer:** Formulário com campos Hostname, TTL, Type, Address, Priority

**Problema 3:** Gmail redirecionou para conta pessoal após setup
- **Solução:** Orientação para adicionar conta profissional no Mail (macOS)
- **Alternativa sugerida:** Adicionar múltiplas contas no Gmail web

### Observações sobre AEServer

- Interface em inglês
- DNS Management disponível no menu lateral "Manage"
- Suporte a todos os tipos de registro: A, AAAA, CNAME, MX, TXT, SRV
- Campo Priority disponível apenas para MX e SRV
- Salvamento via botão "Save Changes" (não automático)
- Propagação DNS: geralmente rápida (minutos), mas pode levar até 48h

### Observações sobre Google Workspace

- Wizard de setup em 3 etapas (personalização opcional)
- Verificação de domínio: TXT record obrigatório
- Ativação Gmail: MX record obrigatório
- DKIM: opcional mas altamente recomendado
- SPF e DMARC: não mencionados no wizard (configuração manual recomendada)
- Chave DKIM 2048-bit gerada automaticamente
- Suporte a múltiplos métodos de verificação (TXT ou CNAME)

---

## Checklist de Validação Pós-Setup

### ✅ Concluído

- [x] Domínio arkstrategy.ae registrado e ativo
- [x] Google Workspace Business Standard contratado
- [x] Usuário marcos@arkstrategy.ae criado
- [x] TXT record de verificação adicionado
- [x] Domínio verificado pelo Google
- [x] MX record adicionado
- [x] Gmail ativado
- [x] DKIM configurado (google._domainkey)
- [x] Email adicionado no Mail (macOS)
- [x] Wizard de personalização completado

### ⏳ Pendente

- [ ] Aguardar propagação DNS completa (24-48h)
- [ ] Enviar email de teste para validar envio/recebimento
- [ ] Adicionar registro SPF
- [ ] Adicionar registro DMARC
- [ ] Configurar assinatura de email profissional
- [ ] Ativar 2FA na conta Google Workspace
- [ ] Criar aliases de email (contact@, info@)
- [ ] Desenvolver website institucional para arkstrategy.ae
- [ ] Integrar email com Command Center CRM
- [ ] Criar templates de email para clientes

---

## Conclusão

Setup completo e funcional do email profissional **marcos@arkstrategy.ae** com Google Workspace Business Standard. Todos os registros DNS críticos (verificação, MX, DKIM) foram adicionados com sucesso no AEServer. Email configurado no cliente Mail (macOS) e pronto para uso.

**Próxima ação recomendada:** Aguardar propagação DNS (24h) e enviar email de teste para validar funcionamento completo.

**Investimento total:** ~USD 238/ano + AED 137/ano para infraestrutura de email profissional de nível empresarial.

---

**Documento gerado em:** 13 de fevereiro de 2026  
**Sessão:** Configuração Google Workspace para ARK Strategy  
**Duração aproximada:** 2 horas  
**Resultado:** ✅ Setup completo e funcional

---

## 9. Criação de Currículos Esportivos (Lucca e Davi) — Slides e PDFs

**Data:** 14 de Fevereiro de 2026
**Status:** Concluída
**Projeto relacionado:** Portes Family (Vg5MNFDfPASJaQBXj97Ssv)

### O que foi feito

**Criação de Currículo Esportivo (Lucca - Sub 16):**
Desenvolvimento inicial em slides HTML (PT/EN) e PDF. Evolução para versão "Nano Banana" (Image Mode): Design premium com renderização de imagens, fundo escuro e integração artística de fotos. Atualização de dados: Inclusão de Al Nasr (2025), ajuste de altura/peso, remoção de "Falso 9". Refinamento visual: Integração de fotos P&B (sem sobreposição), alinhamento de texto em "Conquistas" (2023 e Destaques na mesma linha) e retorno de ícones geométricos no slide de Habilidades.

**Criação de Currículo Esportivo (Davi - Sub 12):**
Desenvolvimento em slides HTML (PT/EN) e PDF seguindo a estrutura da v1 do Lucca. Correções críticas: Ajuste de datas (2013/14 -> 2023/24) e ordenação cronológica decrescente (2025 -> 2020).

**Geração de Documentos:** Conversão de todos os conteúdos para PDF via Markdown (manus-md-to-pdf) para envio como documento estático.

### Decisões técnicas relevantes

- Mudança de Engine de Slides: Para a versão final do Lucca, migrou-se do slide_edit (HTML/CSS editável) para image_slide_generate (Nano Banana) para priorizar impacto visual e composição artística em detrimento da editabilidade direta.
- Pipeline de PDF: Manteve-se a geração de PDFs separada dos slides (via Markdown) para garantir legibilidade em formato A4/Documento, independente do visual da apresentação.
- Integração de Imagens: Na v3 do Lucca, os prompts de geração de imagem foram ajustados para "integrar artisticamente" as fotos ao fundo, evitando o aspecto de colagem simples.

### Pendências e próximos passos

- Upgrade do Davi: O currículo do Davi permanece no formato HTML padrão (v1). Futuramente, pode ser necessário atualizá-lo para o padrão "Nano Banana" para manter consistência visual com o do irmão.
- Vídeo: A solicitação de melhoria de qualidade de vídeo não foi atendida (limitação técnica), sendo substituída pelo uso de fotos estáticas de alta qualidade.

### Arquivos e artefatos

- Projetos de Slides (Lucca - Nano Banana): /home/ubuntu/lucca_curriculo_nb_pt, /home/ubuntu/lucca_curriculo_nb_en
- Projetos de Slides (Davi - Standard): /home/ubuntu/curriculo_davi_pt, /home/ubuntu/curriculo_davi_en
- PDFs Finais: lucca_curriculo_final_v3_pt.pdf, lucca_curriculo_final_v3_en.pdf, curriculo_davi_pt_final.pdf, curriculo_davi_en_final.pdf
- Fontes Markdown: lucca_curriculo_final_v3_*.md, curriculo_davi_*_final.md

---

---

## 10. Criação de Landing Page Ark Hub — Central de Projetos Pessoais

**Data:** 14 de fevereiro de 2026

**Status:** Concluída

**Projeto relacionado:** Ark Group (Lap5wRprqDR5x9DiXU3WBL) / ark-hub (web-static)

### O que foi feito

Desenvolvido projeto web estático completo chamado **Ark Hub** - uma landing page minimalista futurística que funciona como hub centralizado para projetos pessoais do Marcos Portes. 

**Entregas principais:**

1. **Inicialização do Projeto**
   - Scaffold web-static com React 19 + TypeScript + Tailwind CSS 4
   - Configuração de template com shadcn/ui, Lucide React, Wouter
   - Projeto criado em `/home/ubuntu/ark-hub` com versão inicial `5d36b017`

2. **Design e Brainstorming**
   - Análise de 3 abordagens de design (Minimalismo Nórdico, Glassmorphism, Brutalism)
   - Seleção de **Minimalismo Nórdico com Acentos Vibrantes** como filosofia principal
   - Documento `ideas.md` criado com especificações completas de design

3. **Implementação de Componentes**
   - **Home.tsx** (130 linhas): Página principal com header, hero section, grid de 6 cards e footer
   - **ProjectCard.tsx** (85 linhas): Componente reutilizável de card com hover effects, background image support, ícone com scale animation, botão "Abrir" com ExternalLink icon
   - **index.css**: Tema completo com variáveis CSS OKLCH, importação de fontes Geist Display/Mono, customizações Tailwind

4. **Geração de Assets Visuais**
   - Logo Ark em azul profundo (transparente) - `/client/public/images/ark-logo.png`
   - Hero background minimalista - `/client/public/images/hero-background.png`
   - Card backgrounds para Dashboard e Storytelling - `/client/public/images/card-dashboard-bg.png`, `/client/public/images/card-storytelling-bg.png`

5. **Configuração de Cards**
   - **Card 1**: Marcos Personal Dashboard → `https://marcosdash-u55fbtoq.manus.space` (ícone 📊)
   - **Card 2**: Portes Family → `https://portesdash-zzm6mtcn.manus.space/` (ícone 👨‍👩‍👧‍👦)
   - **Card 3**: Ark Pipeline → `https://arkdash-85rzcdsq.manus.space` (ícone 📈)
   - **Card 4**: Ark Technology → `#` (ícone ⚙️, URL pendente)
   - **Cards 5-6**: Placeholders para futuros projetos (ícone 🔗, URLs em branco)

6. **Documentação Completa**
   - Arquivo `ARK_HUB_DOCUMENTACAO_COMPLETA.md` (600+ linhas) com:
     - Visão geral e objetivos
     - Filosofia de design detalhada
     - Arquitetura técnica completa
     - Estrutura de arquivos comentada
     - Código-fonte dos componentes principais
     - Paleta de cores (valores OKLCH + RGB)
     - Sistema tipográfico (Geist Display/Mono)
     - Instruções de uso e navegação
     - Guia passo-a-passo para adicionar novos projetos
     - Configuração e customização

### Decisões técnicas relevantes

1. **Stack Tecnológico**
   - React 19 + TypeScript (type safety)
   - Tailwind CSS 4 com CSS Variables OKLCH (cores modernas, escaláveis)
   - Wouter para routing (lightweight, adequado para single-page app)
   - shadcn/ui para componentes base (Button, etc.)
   - Lucide React para ícones (ExternalLink)
   - Vite como build tool (fast refresh, otimizado)

2. **Design System**
   - **Cores OKLCH**: Azul profundo `oklch(0.5 0.15 250)`, Roxo suave `oklch(0.6 0.12 280)`, Off-white `oklch(0.98 0 0)`
   - **Tipografia**: Geist Display (títulos, bold 700) + Geist Mono (descrições, regular 400) - importadas via Google Fonts
   - **Responsividade**: Mobile-first com breakpoints md (tablet 2 cols) e lg (desktop 3 cols)
   - **Tema**: Light-only (sem dark mode implementado)

3. **Componentes e Estrutura**
   - Array de projetos em Home.tsx (fácil adicionar novos)
   - ProjectCard como componente reutilizável com props: icon, title, description, url, backgroundImage
   - Grid responsivo: `grid gap-8 md:grid-cols-2 lg:grid-cols-3`
   - Cards com altura mínima `min-h-96` para consistência visual

4. **Animações e Interações**
   - Transições suaves em 300ms (`transition-all duration-300`)
   - Hover effects: card sobe 8px (`hover:-translate-y-2`), ícone escala 110% (`group-hover:scale-110`), sombra aumenta (`hover:shadow-lg`)
   - Overlay de background com backdrop blur (`backdrop-blur-sm`)
   - Botão com hover state: bg muda para primary, texto para primary-foreground

5. **Imagens e Assets**
   - Background images opcionais por card (suporte a null)
   - Overlay semi-transparente (85% opacidade) para legibilidade
   - Logo Ark integrada no header (h-10 w-10)
   - Hero section com background image + overlay (70% opacidade)

6. **Deployment**
   - Projeto estático (sem backend necessário)
   - Vite build otimizado para produção
   - Dev server rodando em `https://3000-i9g20qtueqnysvert2qac-26336497.sg1.manus.computer`
   - Pronto para publicação via Manus UI (Publish button)

### Pendências e próximos passos

1. **URLs Pendentes**
   - Ark Technology: URL ainda com `#`, aguardando link do projeto
   - Cards 5-6: Placeholders em branco, aguardando novos projetos do Ark Group

2. **Melhorias Futuras (Opcional)**
   - Adicionar animação de entrada nos cards (fade-in staggered, 100ms delay entre cada)
   - Implementar modo dark (CSS variables já preparadas para suportar)
   - Adicionar busca/filtro de projetos (se número de cards crescer)
   - Integração com API para dados dinâmicos (se necessário)
   - Adicionar página de detalhes ou modal para projetos sem URL definida
   - Implementar analytics (Umami já configurado no template)

3. **Bugs Conhecidos**
   - Parse5 warnings no console (HTML parsing issues) - não afeta funcionalidade, relacionado ao build system
   - Nenhum bug funcional identificado

4. **Manutenção**
   - Documentação completa criada para facilitar manutenção futura
   - Código bem comentado e estruturado
   - Fácil adicionar novos cards (editar array em Home.tsx)

### Arquivos e artefatos

**Arquivos Principais Criados/Modificados:**

```
/home/ubuntu/ark-hub/
├── client/src/pages/Home.tsx                    # Página principal (130 linhas)
├── client/src/components/ProjectCard.tsx        # Componente card (85 linhas)
├── client/src/index.css                         # Tema + estilos globais
├── client/index.html                            # HTML template
├── client/public/images/
│   ├── ark-logo.png                            # Logo Ark azul profundo
│   ├── hero-background.png                     # Hero section background
│   ├── card-dashboard-bg.png                   # Card 1 background
│   └── card-storytelling-bg.png                # Card 2 background
├── ideas.md                                     # Brainstorming de design (175 linhas)
└── package.json                                 # Dependências (React 19, Tailwind 4, etc.)

/home/ubuntu/ARK_HUB_DOCUMENTACAO_COMPLETA.md   # Documentação completa (600+ linhas)
```

**Checkpoints Salvos:**

- `5d36b017` - Inicial (scaffold web-static)
- `81ae98e4` - Landing page com 6 cards e design futurístico
- `d0c3918b` - Cards com 4 preenchidos + 2 em branco
- `a0f321d4` - URLs dos 3 projetos atualizadas (versão final)

**URLs e Links:**

- **Dev Server**: https://3000-i9g20qtueqnysvert2qac-26336497.sg1.manus.computer
- **Marcos Personal Dashboard**: https://marcosdash-u55fbtoq.manus.space
- **Portes Family**: https://portesdash-zzm6mtcn.manus.space/
- **Ark Pipeline**: https://arkdash-85rzcdsq.manus.space
- **Projeto Manus**: ark-hub (web-static, versão a0f321d4)

**Tecnologias Utilizadas:**

- React 19.2.1
- TypeScript 5.6.3
- Tailwind CSS 4.1.14
- Vite 7.1.7
- shadcn/ui (Button, etc.)
- Lucide React 0.453.0
- Wouter 3.3.5
- Geist Display + Geist Mono (Google Fonts)

**Documentação Gerada:**

- `ARK_HUB_DOCUMENTACAO_COMPLETA.md` - Guia completo para Claude/desenvolvedores futuros
- `ideas.md` - Brainstorming de design com 3 abordagens analisadas

---

**Resumo Executivo:** Projeto Ark Hub completamente implementado e documentado. Landing page minimalista futurística com 6 cards (4 funcional, 2 placeholders), design nórdico com acentos azul/roxo, tipografia Geist, responsividade 3-2-1 colunas, hover effects elegantes, pronto para publicação. Documentação extensiva criada para facilitar manutenção e expansão futura.

---

## 11. Reestruturação de Acordo de Dívida com Cenários Mutuamente Excludentes e Proteção Standstill Progressivo

**Data:** 14 de Fevereiro de 2026
**Status:** Concluída
**Projeto relacionado:** Zion Capital (59VqEBrEBgiGVjtdTHdPBk)

### O que foi feito

#### 1. Análise Jurídica e Validação com HAZEL.IA
- Consultou a HAZEL.IA (IA jurídica especializada em lei dos EAU) para validar a estrutura de dois cenários mutuamente excludentes
- Obteve confirmação de que exclusão mútua é válida e executável nos EAU desde que conste no contrato autenticado (não no cheque)
- Validou que a defesa contra dupla apresentação é forte, com direito a medida liminar e indenização
- Recebeu 7 cláusulas-modelo prontas da HAZEL.IA para incorporação no contrato final

#### 2. Reestruturação da Estratégia de Pagamento
**Cenário A - Quitação Total (Ideal):**
- 1 cheque de USD 114.703,90 com vencimento em 14 de Junho de 2026
- Se compensado = quitação total e definitiva
- Cheques 2, 3, 4, 5 tornam-se automaticamente nulos e devem ser devolvidos em 3 dias úteis

**Cenário B - Quitação Progressiva (Contingência):**
- Ativado se Cheque 1 não for compensado
- 4 cheques com valores de DIFERENÇAS (não acumulados):
  - Cheque 2: USD 34.411,17 (30%) - 14/06/2026 - **CRÍTICO: Mínimo obrigatório para validar Cenário B**
  - Cheque 3: USD 22.940,78 (20%) - 14/08/2026
  - Cheque 4: USD 22.940,78 (20%) - 14/10/2026
  - Cheque 5: USD 34.411,17 (30%) - 14/12/2026
- Standstill automático de 60 dias após cada pagamento bem-sucedido
- Long Stop Date: 14 de Dezembro de 2026

**Cláusula Crítica de Validação (3.9):**
- Se Cheque 1 NÃO compensado E Cheque 2 (30% mínimo) NÃO compensado até 14/06/2026 → Cenário B NÃO se ativa
- Credor pode executar imediatamente pela dívida total sem esperar standstill
- Garante boa-fé do devedor ao cumprir limiar mínimo de 30%

#### 3. Criação de Documentação Jurídica Completa

**Documentos Gerados:**
- `Amendment_Debt_Acknowledgement_FINAL_EN.pdf` - Contrato em inglês (14 artigos)
- `Aditamento_Confissao_Divida_FINAL_PT.pdf` - Contrato em português (14 artigos)
- `STORYTELLING_ESTRUTURADO.md` - Guia narrativo para conversa com Marcelo Salazar
- `ROTEIRO_AUDIO.md` - Script pronto para gravação de áudio em 7 partes
- `CHECKLIST_PONTOS_CHAVE.md` - Checklist de segurança com pontos que não podem ser esquecidos
- `ANALISE_HAZEL_RESPOSTA_COMPLETA.md` - Análise jurídica completa da HAZEL.IA
- `PROMPT_HAZEL_COPIAR_COLAR.txt` - Prompt limpo para copiar/colar na HAZEL.IA

#### 4. Estrutura Técnica dos Contratos

**Artigos Inclusos:**
1. Amendment to Payment Structure
2. Acknowledgement of Debt (USD 114.703,90 + USD 4.588,16 juros = USD 119.292,06 total)
3. Mutually Exclusive Payment Scenarios (A e B)
4. Progressive Settlement Plan - Cheques e Standstill Schedule
5. Long Stop Date and Final Deadline (14/12/2026)
6. Conditions for Non-Presentation and Exclusion Clause
7. Cheque Management and Physical Custody
8. Breach of Agreement - Penalties and Remedies (USD 10.000 por violação)
9. Receipt of Full Settlement and Confirmation
10. Commitment to Judicial Installment Payment (Art. 320(2) UAE Civil Procedure Law)
11. Good Faith and Partnership Commitment
12. Governing Law and Jurisdiction (Dubai Courts - Onshore)
13. Entire Agreement
14. Language and Translation (English prevails over Portuguese)

**Tabela de Cheques Incluída:**
- Tabela visual com 5 linhas (Cheque 1-5)
- Colunas: Cheque | Amount (USD) | Percentage | Due Date | Description
- Formatação com cores alternadas (header azul #1B5E8F, linhas alternadas branco/cinza)

#### 5. Geração de PDFs com Layout Profissional

**Abordagem Final (WeasyPrint):**
- Criado script Python `generate_pdfs.py` que usa WeasyPrint para converter HTML/CSS em PDF
- HTML templates com CSS profissional replicando layout do documento original
- Fontes: Calibri/Arial, 11pt para corpo, 20pt para títulos
- Cores: #1B5E8F para títulos e headers (azul corporativo)
- Espaçamento: 0.75in margens, 1.5 line-height para legibilidade
- Tabelas com border-collapse, alternância de cores, padding 0.08in
- Assinaturas formatadas com linhas de 0.5in de altura

**Iterações Anteriores (Descartadas):**
- ReportLab: Gerou PDF mas com layout inadequado
- Markdown to PDF (manus-md-to-pdf): Não manteve formatação profissional
- Motivo da mudança: Necessidade de replicar exatamente o layout do documento original enviado

#### 6. Materiais de Comunicação

**Storytelling para Marcelo Salazar:**
- 7 seções narrativas: Abertura (Empatia) → Objetivo Comum → Contexto → Prova de Caráter → Lógica Financeira → Lado Humano → Apelo Final
- Roteiro de áudio pronto para gravação
- Checklist de pontos-chave para não esquecer durante conversa/áudio
- Possíveis objeções e respostas rápidas incluídas

### Decisões técnicas relevantes

#### 1. Estrutura de Cenários Mutuamente Excludentes
- **Decisão:** Implementar dois cenários com exclusão automática em vez de simples parcelamento
- **Justificativa:** Oferece segurança ao credor (quitação total possível) e flexibilidade ao devedor (standstill progressivo se necessário)
- **Trade-off:** Complexidade contratual aumenta, mas cláusulas validadas pela HAZEL.IA garantem executoriedade nos EAU
- **Impacto:** Requer notarização conjunta de todos os 5 cheques com o contrato

#### 2. Cláusula de Validação do Cenário B (Mínimo 30%)
- **Decisão:** Exigir compensação de Cheque 2 (30%) até 14/06/2026 para ativar Cenário B
- **Justificativa:** Demonstra boa-fé do devedor e protege credor contra abandono total
- **Risco Mitigado:** Evita cenário onde devedor não paga Cheque 1 nem Cheque 2 e ainda ativa standstill
- **Impacto:** Se Cheque 2 não compensado até 14/06, credor pode executar pela dívida total imediatamente

#### 3. Standstill Progressivo de 60 Dias
- **Decisão:** 60 dias de standstill após cada compensação bem-sucedida (não apenas após primeira)
- **Justificativa:** Incentiva pagamentos progressivos e oferece períodos de respiro previsíveis
- **Cronograma:** 14/06 (Cheque 2) → 60 dias → 14/08 (Cheque 3) → 60 dias → 14/10 (Cheque 4) → 60 dias → 14/12 (Cheque 5)
- **Impacto:** Long Stop Date fixo em 14/12/2026 não se estende; standstill apenas adia apresentação de próximos cheques

#### 4. Valores em Diferenças, Não Acumulados
- **Decisão:** Cheques 2-5 representam diferenças (30%, 20%, 20%, 30%) não valores acumulados
- **Justificativa:** Evita confusão e dupla contagem; cada cheque é independente
- **Verificação:** USD 34.411,17 + 22.940,78 + 22.940,78 + 34.411,17 = USD 114.703,90 ✓
- **Impacto:** Clareza contratual reduz risco de litígio interpretativo

#### 5. Lei dos EAU e Jurisdição Dubai Courts
- **Decisão:** Governança por UAE Federal Law No. 5 of 1985 (Civil Transactions Law) + Decree-Law No. 15 of 2024
- **Justificativa:** Ambas as partes têm conexão com EAU; Dubai Courts reconhecem cheques pós-datados como títulos executivos
- **Alternativa Considerada:** Lei brasileira (rejeitada por complexidade de execução internacional)
- **Impacto:** Notarização em Dubai Courts Notary ou DIFC Courts Notary é obrigatória

#### 6. Penalidade Contratual de USD 10.000 por Violação
- **Decisão:** Penalidade objetiva (não proporcional) por cada apresentação ilegal de cheque
- **Justificativa:** Desincentiva má-fé do credor; cálculo simples e previsível
- **Alternativa Considerada:** Penalidade proporcional (rejeitada por dificuldade de comprovação de danos)
- **Impacto:** Credor tem incentivo claro para respeitar exclusão mútua e datas de vencimento

#### 7. Geração de PDF com WeasyPrint
- **Decisão:** Usar WeasyPrint (HTML/CSS → PDF) em vez de ReportLab ou Markdown converter
- **Justificativa:** WeasyPrint oferece melhor controle de layout, cores, fontes e tabelas; HTML/CSS é mais flexível que Python direto
- **Trade-off:** Requer renderização HTML completa; mais lento que ReportLab mas resultado visual superior
- **Impacto:** PDFs gerados com layout profissional idêntico ao original, pronto para notarização

### Pendências e próximos passos

#### Ações Imediatas (Críticas)
1. **Revisão por Advogado Local em Dubai**
   - Levar ambos os PDFs (EN e PT) para revisão jurídica
   - Validar conformidade com práticas notariais de Dubai
   - Confirmar se notarização conjunta (contrato + 5 cheques) é possível em um único ato
   - Prazo: Antes de qualquer apresentação a Marcelo Salazar

2. **Gravação de Áudio para Marcelo Salazar**
   - Usar `ROTEIRO_AUDIO.md` como script
   - Gravar em local silencioso, tom natural, deixar emoção sair
   - Enviar áudio + PDFs + CHECKLIST_PONTOS_CHAVE para referência
   - Prazo: Assim que possível (antes de 21/02/2026 idealmente)

3. **Preparação dos 5 Cheques Pós-datados**
   - Emitir 5 cheques com valores e datas exatas conforme tabela
   - Cheques devem estar em nome de Marcelo Salazar Filho
   - Manter em local seguro até notarização
   - Prazo: Antes da notarização

#### Ações de Médio Prazo
4. **Notarização em Dubai**
   - Agendar notarização no Dubai Courts Notary ou DIFC Courts Notary
   - Levar: Contrato (EN ou PT), 5 cheques, passaportes/IDs
   - Solicitar cópias autenticadas para ambas as partes
   - Prazo: 14-21 dias após aprovação de Marcelo Salazar

5. **Entrega Formal a Marcelo Salazar**
   - Entregar contrato notarizado + 5 cheques notarizados
   - Solicitar assinatura de recebimento
   - Manter cópia autenticada em local seguro
   - Prazo: Imediatamente após notarização

#### Riscos e Mitigações
- **Risco:** Marcelo Salazar rejeita Cenário B ou exige modificações
  - **Mitigação:** Áudio com storytelling e checklist de pontos-chave ajuda convencimento; HAZEL.IA validou estrutura
  
- **Risco:** Notário em Dubai questiona exclusão mútua ou standstill
  - **Mitigação:** Levar análise da HAZEL.IA como suporte; cláusulas seguem precedentes nos EAU
  
- **Risco:** Cheque 1 não é compensado mas Cheque 2 também não (ativa cláusula 3.9)
  - **Mitigação:** Contrato claro; Marcelo Salazar pode executar imediatamente; risco calculado e aceito
  
- **Risco:** Discrepância entre versões EN e PT causa litígio interpretativo
  - **Mitigação:** Cláusula 14.1 estabelece que versão EN prevale; ambas as versões foram traduzidas com cuidado jurídico

#### Melhorias Futuras (Não Críticas)
- Adicionar apêndice com cronograma visual (Gantt chart) dos standstills
- Criar template de "Recibo de Quitação Total e Definitiva" para usar após Cenário A ou B
- Preparar modelo de "Notificação de Ativação de Cenário B" para enviar a Marcelo Salazar se Cheque 1 não for compensado
- Traduzir CHECKLIST_PONTOS_CHAVE para português para facilitar comunicação com Marcelo

### Arquivos e artefatos

#### Documentos Jurídicos Finais
- `/home/ubuntu/Amendment_Debt_Acknowledgement_FINAL_EN.pdf` - Contrato em inglês, 14 artigos, layout profissional, pronto para notarização
- `/home/ubuntu/Aditamento_Confissao_Divida_FINAL_PT.pdf` - Contrato em português, 14 artigos, layout profissional, pronto para notarização

#### Documentos de Suporte Jurídico
- `/home/ubuntu/ANALISE_HAZEL_RESPOSTA_COMPLETA.md` - Análise completa da HAZEL.IA com 7 cláusulas-modelo e validações
- `/home/ubuntu/PROMPT_HAZEL_COPIAR_COLAR.txt` - Prompt limpo para consultas futuras com HAZEL.IA

#### Materiais de Comunicação e Storytelling
- `/home/ubuntu/STORYTELLING_ESTRUTURADO.md` - Guia narrativo em 7 seções para conversa com Marcelo Salazar
- `/home/ubuntu/ROTEIRO_AUDIO.md` - Script pronto para gravação de áudio, 7 partes estruturadas
- `/home/ubuntu/CHECKLIST_PONTOS_CHAVE.md` - Checklist de segurança com pontos-chave, objeções e respostas

#### Arquivos de Suporte (Markdown Intermediários)
- `/home/ubuntu/Amendment_Debt_Acknowledgement_FINAL_EN_v2.md` - Versão Markdown do contrato EN (descartada em favor de PDF)
- `/home/ubuntu/Aditamento_Confissao_Divida_FINAL_PT_v2.md` - Versão Markdown do contrato PT (descartada em favor de PDF)

#### Scripts de Geração
- `/home/ubuntu/generate_pdfs.py` - Script Python com WeasyPrint que gera ambos os PDFs (EN e PT) com layout profissional
- `/home/ubuntu/create_amendment_pdf.py` - Script ReportLab anterior (descartado, mantido para referência)

#### Documentos Originais de Referência
- `/home/ubuntu/upload/Amendment_Debt_Acknowledgement_MarceloSalazar_EN.pdf` - PDF original enviado pelo usuário (usado como modelo de layout)

#### Contexto do Projeto
- **Projeto Zion Capital:** 59VqEBrEBgiGVjtdTHdPBk
- **Partes Envolvidas:** 
  - Devedor: Mr. Marcos Paulo Rezende Portes (FY284219, 784-1990-271212-0)
  - Credor: Mr. Marcelo Salazar Filho (CPF: 028.420.184-78, RG: 4566824)
- **Dívida Original:** USD 114.703,90 (3 contratos ZION CAPITAL LTDA)
- **Dívida Total com Juros:** USD 119.292,06 (1% ao mês de 14/02 a 14/06/2026)

#### Tecnologias Utilizadas
- **Python 3.11:** Scripts de geração de PDF
- **WeasyPrint:** Conversão HTML/CSS → PDF profissional
- **HTML5/CSS3:** Templates de layout para contratos
- **Markdown:** Documentação estruturada
- **HAZEL.IA:** Consultoria jurídica especializada em lei dos EAU

---

**Resumo Executivo:** Reestruturação bem-sucedida de acordo de dívida com dois cenários mutuamente excludentes, validada juridicamente pela HAZEL.IA, com cláusula crítica de 30% mínimo para validação do Cenário B. Contratos gerados em inglês e português com layout profissional pronto para notarização em Dubai. Materiais de comunicação (storytelling, roteiro de áudio, checklist) preparados para apresentação a Marcelo Salazar. Próximo passo crítico: revisão por advogado local em Dubai antes de qualquer apresentação formal.

---

## Fluxo de Atualização

**No início de cada sessão nova:**
1. Ler este arquivo do repositório GitHub para carregar o contexto.

**No final de cada sessão que gere trabalho relevante:**
1. Gerar resumo da sessão no formato padrão (O que foi feito / Decisões técnicas / Pendências / Arquivos).
2. Fazer append neste arquivo e comitar no repositório.

---

*Documento criado em 14 de Fevereiro de 2026. Mantido automaticamente pelo Manus Agent.*
