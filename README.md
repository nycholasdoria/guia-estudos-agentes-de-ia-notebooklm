# guia-estudos-agentes-de-ia-notebooklm

## 🎯 1. Contexto e Objetivos

### 💡 Por que este tema?
A evolução da Inteligência Artificial ultrapassou as respostas em texto: o mercado agora demanda sistemas capazes de executar ações e resolver problemas de ponta a ponta. 

Estruturar processos, desenhar fluxos de automação e implementar sistemas agênticos autônomos são áreas de altíssima relevância no mercado de tecnologia atual. Este projeto nasceu da necessidade de explorar e dominar essas tecnologias mais profundamente.

### 🧠 O "Segundo Cérebro"
Utilizando o **Gemini NotebookLM**, foi construída uma base de conhecimento com fontes confiáveis (vídeos, documentações da IBM e do Google e guias de referência da OpenAi). Esse caderno temático atua como um "segundo cérebro" digital para centralizar, cruzar referências e acelerar o domínio prático sobre o tema.

### 🎯 Objetivos de Aprendizagem
- **Conceitual:** Compreender conceitos básicos dos modelos tradicionais de linguagem (LLMs/Chatbots) e como eles funcionam na prática.
- **Técnico:** Entender a arquitetura dos agentes, como podem tomar decisões e o uso de ferramentas (tools) via APIs, as famosas Function Calling;
- **Estratégico / Negócios:** Mapear casos reais de aplicação, automação de fluxos operacionais e modelos de geração de valor para empresas.

## 📚 2. Curadoria de Fontes

Este caderno está vinculado a conteúdos de alta autoridade técnica e visão prática de mercado, foram selecionadas fontes abertas em diferentes formatos:

| Formato | Fonte / Autor | Título / Tema Principal | Acesso |
| :---: | :--- | :--- | :---: |
| 🎬 **Vídeo** | Liam Ottley (YouTube) | *How to Build & Sell AI Agents in 2026: Ultimate Beginner’s Guide* (Conceitos de trabalhadores digitais e casos práticos) | [Assistir](https://www.youtube.com/watch?v=5TxSqvPbnWw) |
| 🎬 **Vídeo** | YouTube | *Tutorial Prático de Agentes e Automações* | [Assistir](https://www.youtube.com/watch?v=AYQtRqW1xX4) |
| 📄 **Artigo** | IBM Think | *Guia para Agentes de IA: Conceitos, Arquitetura e Aplicações* | [Ler artigo](https://www.ibm.com/br-pt/think/ai-agents#605511093) |
| 📄 **Artigo** | Google Cloud Discover | *O que são agentes de IA? Definição, exemplos e tipos* | [Ler artigo](https://cloud.google.com/discover/what-are-ai-agents?hl=pt-BR) |
| 📑 **PDF** | OpenAI | *A Practical Guide to Building AI Agents* (Arquitetura, Tools e Melhores Práticas) | `Disponível no repositório` |

> 💡 **Nota:** O arquivo `a-practical-guide-to-building-agents.pdf` foi adicionado à pasta deste repositório para consulta pública e reprodução deste projeto.
---

## 🧪 3. Engenharia de Prompts & "Cicatrizes"

Foram realizados testes de prompts para explorar como o Gemini NotebookLM elabora respostas a versões diferentes de prompt para um mesmo assunto. Essa etapa, apresenta perguntas diretas, comandos imperativos, especificações, definição de persona e restrições.

### 🔬 Teste 1: Diferença entre Agentes de IA e Chatbots Tradicionais

#### 🔄 Etapas de Teste:
- **Prompt 1 (Pergunta simples e aberta):**
  > *"O que são agentes de IA e como eles se diferenciam dos chatbots comuns? Use casos práticos do dia a dia para exemplificar."*
- **Prompt 2 (Prompt 1 + Rastreabilidade):**
  > *"...Além disso, indique em qual fonte veio a informação fornecida. Se for texto, detalhe em qual página encontrou informação. Se for vídeo, indique as horas e minutos."*
- **Prompt 3 (Modo Imperativo + Lista de passo a passo + Definição de Persona - Versão Final):**
  > "Explique o que são agentes de IA e como eles se diferenciam dos chatbots comuns:  
  > 1. Explique de uma forma que uma criança de 5 anos entenderia;  
  > 2. Use casos práticos do dia a dia para exemplificar;  
  > 3. Indique de qual fonte veio a informação fornecida (página para textos e minuto/segundo para vídeos)."

#### 💡 Aprendizados e "Cicatrizes" do Teste 1:
- **O poder do modo imperativo:** Comandos diretos são objetivos, específicos, claros e evita ambiguidade. Além disso, eles geram respostas mais estruturadas, economia tokens e tempo de leitura.
- **Definição de Persona de 5 anos:** Forçou a IA a abandonar termos técnicos e criar a metáfora simples de fácil compreensão como do *"garçom que apenas lê o cardápio"* (chatbot) vs. *"trabalhador digital que executa a tarefa inteira"* (agente).
- **Rastreabilidade cirúrgica:** O NotebookLM localizou com precisão referências como as páginas 4 e 7 do PDF da OpenAI e o intervalo de 07:00 a 15:00 do vídeo do Liam Ottley. Desse modo, te dá liberdade de consultar o ponto exato do material bruto.

---

### 🔬 Teste 2: O Funcionamento de APIs e Chamadas de Ferramentas (Tools)

#### 🔄 Etapas de Teste:
- **Prompt 1 (Zero Shot):**
  > "Explique o que é API e como os agentes a usam."
  *Resultado:* Resposta didática, porém insistiu no exemplo do garçom e deu exemplos genéricos de requisições.
- **Prompt 2 (Restrição Negativa + Citações das Fontes - Versão Final):**
  > "Explique o que é API e como os agentes a usam. Seja extremamente didático e utilize outra analogia, sem ser a do garçom para explicar como a API funciona. Mostre casos práticos das chamadas de API citados nas fontes."

#### 💡 Aprendizados e "Cicatrizes" do Teste 2:
- **Restrições negativas funcionam:** Ao proibir a analogia do garçom, o modelo criou a metáfora do **Drive-Thru de Fast-Food**, ilustrando com perfeição o conceito de encapsulamento e parâmetros de entrada/saída (inputs/outputs).
- **Extração de Arquitetura Real:**  Aqui ocorreu algo interessante. Com prompt refinado, a IA a parou de inventar **exemplos abstratos** e buscou casos reais presentes nas fontes do notebook. Assim, abordou a aplicabilidade prática do assunto de forma mais técnica, o que é essencial para o aprofundamento do assunto.
  - **Google Geocoding + Google Solar API (GET):** Conversão de endereço e cálculo solar via satélite.
  - **Sales Co-pilot (SerpAPI + Apify + Firecrawl):** Encadeamento de chamadas para prospecção de leads.
  - **Leitura de Recibos (Telegram + Google Sheets + Gmail):** Automação com verificação condicional (disparo de e-mail para despesas acima de $500).
  - **Telefonia por IA (Vapi API):** Requisições POST para `/call/phone` e GET em `/call/{id}` para transcrição.

---

### 🩹 Quadro Resumo das "Cicatrizes" (Troubleshooting)

| Desafio Encontrado | Sintoma / Resposta Inicial | Solução de Prompt Aplicada | Resultado Final |
| :--- | :--- | :--- | :--- |
| **Respostas genéricas ou clichês** | A IA repetiu analogias batidas (ex: garçom). | Aplicação de **restrição negativa** explícita (*"sem ser a do garçom"*). | Metáfora original do Drive-Thru, mantendo a didática e o rigor técnico. |
| **Falta de rastreabilidade das fontes** | Informação correta, mas sem ancoragem comprovada. | Inclusão de **parâmetros de citação estrita** (páginas e timestamps). | Identificação exata no PDF da OpenAI e nos minutos dos vídeos. |
| **Exemplos puramente teóricos** | "Consultar o tempo" ou "preço de ações". | Comando imperativo exigindo **casos práticos citados nas fontes**. | Extração de arquiteturas completas com múltiplos serviços e métodos HTTP. |

> 💡 **Nota:** O arquivo `Teste-de-prompt.md` foi adicionado à pasta deste repositório para consulta pública e compreensão melhor das análises dos prompts.
---

