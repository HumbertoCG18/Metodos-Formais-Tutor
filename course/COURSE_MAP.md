# COURSE_MAP — Metodos-Formais

> **Como usar:** Este arquivo define a ordem pedagógica dos tópicos.
> O tutor consulta este mapa para saber o que o aluno já deveria ter visto
> e o que ainda não foi apresentado formalmente.
> Cronograma completo disponível em `course/SYLLABUS.md`

## Estrutura do curso

### Unidade 01 — Métodos Formais
- [ ] 1.1. Sistemas Formais
- [ ] 1.2. Linguagens de Especificação e Lógicas
- [ ] 1.2.1. Fundamentos de Lógica de Primeira Ordem
- [ ] 1.2.2. Especificação de Conjuntos Indutivos
- [ ] 1.2.3. Especificação de Funções Recursivas
- [ ] 1.3. Abordagens para Verificação Formal
- [ ] 1.3.1. Verificação de Modelos (Model Checking)
- [ ] 1.3.2. Verificação de Programas
- [ ] 1.3.3. Provadores de Teoremas
- [ ] 1.4. Exemplos de Aplicações

### Unidade 02 — Verificação de Programas
- [ ] 2.1. Lógica de Hoare
- [ ] 2.1.1. Pré e Pós Condições
- [ ] 2.1.2. Correção Parcial e Total
- [ ] 2.1.3. Invariante e Variante de Laço
- [ ] 2.1.4. Sistema de Prova
- [ ] 2.2. Softwares de Suporte à Verificação Formal de Programas (Dafny)

### Unidade 03 — Verificação de Modelos
- [ ] 3.1. Máquinas de Estado
- [ ] 3.1.1. Modelos de Kripke
- [ ] 3.2. Fundamentos de Lógicas Temporais
- [ ] 3.2.1. Lógica Temporal Linear (LTL)
- [ ] 3.2.2. Lógica Temporal Ramificada (CTL)
- [ ] 3.3. Especificação de Propriedades para Sistemas Sequenciais e Concorrentes
- [ ] 3.4. Softwares de Suporte à Verificação Formal de Modelos

---

## Timeline — Cronograma × Unidades

> Mapeamento cruzado entre o cronograma (`course/SYLLABUS.md`) e as unidades do plano de ensino.
> O tutor usa esta tabela para saber em qual unidade o aluno está baseado na data atual.
> **Atualizado em:** 2026-03-25

| Unidade | Período (início → fim) | Aulas | Slug (referência) |
|---|---|---|---|
| Unidade 01 — Métodos Formais | 04/03/2026 → 22/04/2026 (pré-P1) | Aulas 2–14 | `unidade-01-métodos-formais` |
| **P1** | **22/04/2026** | Aula 15 | — |
| Unidade 02 — Verificação de Programas | 27/04/2026 → 06/07/2026 (pré-P2) | Aulas 16–35 | `unidade-02-verificação-de-programas` |
| **P2** | **06/07/2026** | Aula 36 | — |
| Unidade 03 — Verificação de Modelos | 15/06/2026 → 24/06/2026 | Aulas 30–33 | `unidade-03-verificação-de-modelos` |

> **Nota:** A Unidade 03 (Verificação de Modelos) ocorre **dentro do período da Unidade 02** no cronograma,
> entre as aulas 30 e 33 (15/06 → 24/06). Ambas são cobradas na P2.

### Detalhamento da Unidade 01 por aula

| Aula | Data | Tópico |
|---|---|---|
| 1 | 02/03/2026 | Apresentação da disciplina |
| 2 | 04/03/2026 | Introdução a Métodos Formais |
| 3 | 09/03/2026 | Revisão de lógica de predicados + Exercícios |
| 4 | 11/03/2026 | Conjuntos indutivos e equações recursivas |
| 5 | 16/03/2026 | Exercícios |
| 6 | 18/03/2026 | Estudo de caso: listas |
| 7 | 23/03/2026 | Estudo de caso: árvores |
| 8 | 25/03/2026 | Exercícios ← **HOJE** |
| 9 | 30/03/2026 | Provas por indução |
| 10 | 01/04/2026 | Provas por indução: listas e árvores |
| 11 | 06/04/2026 | Prova Interativa de Teoremas — Isabelle |
| 12 | 08/04/2026 | Prova Interativa de Teoremas — Isabelle (Lab) |
| 13 | 13/04/2026 | Exercícios (Lab) |
| 14 | 15/04/2026 | Exercícios de revisão |
| — | 20/04/2026 | Suspensão de aulas |
| **P1** | **22/04/2026** | **Prova P1** |

---

## Tópicos de alta incidência em prova

> Mapeamento baseado nos tópicos do SYLLABUS e na estrutura de material disponível.
> A P1 cobre 100% da Unidade 01.

| Tópico | Unidade | Incidência estimada | Observação |
|---|---|---|---|
| Conjuntos Indutivos (axiomas, regras, árvores de prova) | 01 | ⭐⭐⭐ Alta | Aula 4, material curado disponível |
| Lógica de Predicados — Sintaxe e Semântica | 01 | ⭐⭐⭐ Alta | Aulas 3, material curado disponível |
| Especificação de Funções Recursivas (listas e árvores) | 01 | ⭐⭐⭐ Alta | Aulas 6–7, múltiplas listas de exercícios |
| Provas por Indução | 01 | ⭐⭐⭐ Alta | Aulas 9–10, direto antes da P1 |
| Lógica Proposicional — Sintaxe e Semântica | 01 | ⭐⭐ Média | Base para lógica de predicados |
| Introdução a MF / Verificação Formal (conceitos) | 01 | ⭐ Baixa | Contextual — pode aparecer em questões teóricas |
| Lógica de Hoare — Pré/Pós condições, Invariantes | 02 | ⭐⭐⭐ Alta | Foco principal da P2 |
| Dafny — verificação de programas | 02 | ⭐⭐⭐ Alta | Aulas 11–29, componente de laboratório |
| Lógicas Temporais (LTL, CTL) | 03 | ⭐⭐ Média | Aulas 30–33, cai na P2 |

---

## Notas do professor

> Baseado na análise do cronograma e material disponível — 2026-03-25.

- A P1 ocorre em **22/04/2026** — restam aproximadamente **4 semanas** a partir de hoje (25/03).
- Os tópicos **Provas por Indução** e **Isabelle** ainda NÃO foram vistos em aula (aulas 9–12 são futuras).
- O conteúdo visto até hoje (25/03) cobre: Introdução a MF, Lógica de Predicados (revisão), Conjuntos Indutivos, Funções Recursivas (listas), Funções Recursivas (árvores).
- A disciplina usa **Dafny** como ferramenta principal de verificação de programas na Unidade 02.
- A ferramenta **Isabelle** é usada como provador interativo de teoremas na Unidade 01 (aulas 11–12).