# Formulário Educação Continuada — Vitru (Unificado)

## O que é este projeto

Sistema web unificado de registro de matrículas de Educação Continuada para as bandeiras **UNICESUMAR** e **Uniasselvi**, operado pela equipe **Contact Sales** da Vitru. Aplicação 100% estática (HTML/JS), usando **Supabase** como backend e **GitHub Pages** como hospedagem.

---

## Arquivos do projeto

| Arquivo | Função |
|---|---|
| `index.html` | Formulário principal de registro de matrículas |
| `dashboard.html` | Painel analítico consolidado + por bandeira |
| `CLAUDE.md` | Documentação do projeto |

---

## Backend — Supabase

**Projeto Supabase:** `ed-continuada-vitru`
**URL:** `https://hnzjveincaygawjttngv.supabase.co`
**Anon Key:** `sb_publishable_us2dvtADt7a7yk8SBXZPUA_gugW3otS`

**Tabela principal:** `matriculas_ed_cont`

| Coluna | Tipo | Descrição |
|---|---|---|
| id | uuid | PK automático |
| consultor | text | Nome do consultor |
| bandeira | text | 'Uniasselvi' ou 'UNICESUMAR' |
| data_matricula | date | Data da matrícula |
| nome_aluno | text | Nome completo do aluno |
| celular | text | Telefone do aluno |
| matricula | text | Nº da matrícula |
| polo | text | Polo de atendimento |
| produto | text | Pós Graduação / Profissionalizante / Técnico / Cursos Livres Shopee |
| produto_descricao | text | Descrição manual (apenas para Shopee) |
| status | text | Pago / Aguardando pagamento / Contrato Gerado |
| ticket_link | text | Ticket (Blip) ou Link (OmniChat) |
| tipo_conversao | text | Tipo de conversão |
| canal_venda | text | Sede / HAG / Home Agent |
| registrado_em | timestamptz | Timestamp automático |

---

## Identidade Visual — Vitru

| Cor | Hex | Uso |
|---|---|---|
| Roxo escuro (fundo) | `#0F0720` | Background da página |
| Roxo card | `#1A0D38` | Cards e containers |
| Roxo input | `#231450` | Inputs e campos |
| Roxo borda | `#3D2A6B` | Bordas |
| Violeta (destaque) | `#8B5CF6` | Acento principal |
| Dourado (estrela) | `#F5C518` | Acento secundário (asterisco Vitru) |
| Texto | `#F0E6FF` | Texto principal |
| Texto2 | `#B09DC8` | Texto secundário |

---

## Campos do formulário

| # | Campo | Tipo | Opções |
|---|---|---|---|
| 1 | Consultor | Select | Lista de 52 consultores |
| 2 | Bandeira | Select | Uniasselvi / UNICESUMAR |
| 3 | Data da Matrícula | Date | — |
| 4 | Nome do Aluno | Text | — |
| 5 | Celular | Tel | — |
| 6 | Matrícula | Text | — |
| 7 | Polo | Text | — |
| 8 | Produto | Select + Sub-campo | Pós Graduação / Profissionalizante / Técnico / Cursos Livres Shopee |
| 8b | Descrição do Curso | Text | Livre (aparece apenas quando Shopee) |
| 9 | Status | Select | Pago / Aguardando pagamento / Contrato Gerado |
| 10 | Ticket / Link da Conversa | Text | — |
| 11 | Tipo de Conversão | Text | — |
| 12 | Canal de Venda | Select | Sede / HAG / Home Agent |

---

## Consultores (52)

Ana Karoline Cristo Ribeiro, Ana Paula De Sousa Leal, Amanda Da Silva Martins, Beatriz Cristina Da Rocha Silva, Beatriz Dos Santos Ribeiro, Beatriz Moreira De Maria, Beatriz Shiki Portilho, Bianca Santos Souza, Bruna Regina Da Silva Justino, Claudia Azuaga, Claudia Cristiane De Almeida Silva, Danubia Cristina Estecio De Oliveira, Elaine Fernandes Boaventura, Elaine Kubitz, Elis Danieli Maia Da Silva, Eloisa Procópio Da Veiga, Emily Emanuelly De Souza, Erica Machado Maia De Oliveira, Evelin Cristini Da Silva, Flavia Cristina Dos Santos Sousa, Flavia Naiara Sales Da Costa, Franciele Moreira De Souza, Gabriela Moreira Da Silva, Gislaine Angélica Rodrigues Silva, Helen Almeida Maffioletti, Helio Gabriel Dos Santos, Iara Patricia Pinheiro Da Silva, Ingrid Aparecida Dos Santos Lares Da Silva, Ivan Marques Daniel, Ivoneide Silva Fernandes, Jaqueline Silva Leal, Juliana Rosa Marinho, Karolyne Aparecida Díaz, Karoline Fagundes Guilhem, Larissa Abade De Almeida, Leila Eduarda Dos Santos, Lidia Venancio Moura, Luane Nepomuceno Dos Passos, Luciana Simili Crecencio, Malu Amaral Kanda, Maria Heloisa Da Silva Dourado, Mariana Ferreira Gomes Barbosa, Mariane Oliveira Dias, Mayara Parras Gomes, Natalia Almeida Lima Morais, Rosana Claudia Faleiro, Rosangela De Souza Ramos, Roseli Cristina Vieira De Lima, Sarah Da Silva Purnucena, Talita Costa Ferreira, Wanessa Cristina Martinelli Camargo Da Costa

---

## Dashboard — Estrutura

### Visões
- **Consolidado** — todas as bandeiras
- **UNICESUMAR** — filtrado
- **Uniasselvi** — filtrado

### Filtros (topo)
- Período (De / Até)
- Produto (dropdown)
- Bandeira (Consolidado / UNICESUMAR / Uniasselvi)

### KPIs (cards)
Cada card exibe: Total acumulado | Qtd semana atual | Variação % vs. semana anterior
- Total de Matrículas
- SEDE
- HOME (Home Agent)
- HAG

### Componentes
- Participação % por operação (SEDE / HOME / HAG)
- Ranking por consultor (exclui HOME)
- Tabela volume por produto (SEDE / HOME / HAG / % participação)
- Evolução temporal (Mês / Semana) por canal

### Regras de semana
- **UNICESUMAR:** terça → segunda
- **Uniasselvi:** segunda → sábado

### Regra HOME
Consultores da operação Home Agent **nunca** aparecem no ranking individual.

---

## Senhas do sistema

| Acesso | Senha |
|---|---|
| Dashboard | `EdCont@2026` |
| Cadastrar Colaborador | `EdCont@2026` |

---

## GitHub Pages

**Conta:** `vitrucontactSales`
**Repositório:** `vitrucontactSales/ed-continuada-vitru`
**URL pública:** `https://vitrucontactsales.github.io/ed-continuada-vitru/`

---

## Status do projeto

- [x] Pasta e estrutura criadas
- [x] CLAUDE.md com contexto completo
- [x] Supabase configurado — tabela `matriculas_ed_cont` criada e testada
- [x] `index.html` — formulário completo e funcionando
- [x] GitHub repositório criado
- [ ] `dashboard.html` — painel analítico
- [ ] Publicar `dashboard.html` no GitHub Pages
