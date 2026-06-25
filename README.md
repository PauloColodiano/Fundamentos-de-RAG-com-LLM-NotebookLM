# 📚 Introdução a RAG e Aplicações com LLMs

LINK: https://notebooklm.google.com/notebook/f5a50ea7-5b3c-489b-972e-b269e9c94c11

## 🎯 Objetivo

Este projeto tem como objetivo introduzir os conceitos fundamentais de **Retrieval-Augmented Generation (RAG)**, suas aplicações práticas e a construção de soluções utilizando **Large Language Models (LLMs)** e a linguagem de programação **Python**.

Além do estudo teórico, foi realizada uma investigação sobre a aplicação de RAG em cenários corporativos, incluindo automação, integração com ferramentas externas e análise de problemas comuns de implementação.

---

## 🧠 O que é RAG?

**Retrieval-Augmented Generation (RAG)** é uma arquitetura que combina a capacidade de geração de texto dos LLMs com a recuperação de informações em bases externas de conhecimento.

Seu objetivo é reduzir alucinações e fornecer respostas mais precisas e atualizadas, utilizando documentos proprietários ou fontes externas durante o processo de geração.

---

## 🎯 Objetivos de Aprendizagem

Ao final deste estudo, busquei responder às seguintes perguntas:

- O que é RAG e quais são seus princípios?
- Qual a diferença entre RAG e Fine-Tuning?
- Quando utilizar um sistema RAG?
- Como funciona uma arquitetura RAG?
- Como embeddings e bancos vetoriais funcionam?
- Quais são as limitações dessa abordagem?
- Como implementar aplicações reais utilizando Python e LLMs?
- Como diagnosticar e resolver problemas em sistemas RAG?

---

## 📖 Curadoria de Fontes

### Vídeos

1. https://www.youtube.com/watch?v=0krh207vts0
2. https://www.youtube.com/watch?v=adbLMhi7A5E
3. https://www.youtube.com/watch?v=CuPKOGdA46Q
4. https://www.youtube.com/watch?v=_-zE9mZVGWc

### Material Complementar

- Slides NVIDIA: **Build RAG with LLMs**

---

## ❓ Perguntas Estratégicas

### Conceitos Fundamentais

1. Quais são os princípios do RAG? Ele é uma vertente dos LLMs?
2. Qual a diferença entre Fine-Tuning e RAG?
3. Quando utilizar RAG e quando apenas um LLM é suficiente?
4. Quais são os componentes de uma arquitetura RAG?
5. O que são embeddings e qual seu papel no RAG?
6. Como funciona um banco vetorial?
7. O RAG substitui bancos de dados tradicionais?
8. Quais são as limitações do RAG?

### Aplicações Práticas

9. É possível criar um agente de automação no WhatsApp utilizando RAG?
10. Como construir esse agente passo a passo?
11. Como integrar RAG com Google Workspace e Google Calendar?
12. Como posso me aprofundar mais nesse assunto?

---

## 🔬 Engenharia de Prompts e Troubleshooting

### Problema 1

**Pergunta**

> Como melhorar um sistema RAG?

**Principais Aprendizados**

- Melhorar a qualidade e limpeza dos dados;
- Utilizar estratégias adequadas de chunking;
- Aplicar Query Augmentation e RAG Fusion;
- Utilizar Rerankers para aumentar a relevância dos documentos;
- Implementar métricas de avaliação utilizando RAGAS;
- Criar Guardrails para segurança e controle de acesso.

---

### Problema 2

**Pergunta**

> Meu sistema RAG está retornando documentos irrelevantes.

**Possíveis causas identificadas:**

#### Chunking inadequado

- Chunks muito grandes geram ruído;
- Chunks muito pequenos perdem contexto;
- Falta de pré-processamento dos documentos.

#### Problemas de Embeddings

- Modelo genérico para domínio específico;
- Embeddings inadequados para consultas assimétricas.

#### Banco Vetorial

- Recuperação baseada apenas em similaridade matemática;
- Baixa relevância semântica.

#### Configuração de Top-K

- Top-K elevado adiciona documentos irrelevantes;
- Top-K baixo pode ocultar informações importantes;
- Ausência de Rerankers.

**Aprendizado Obtido**

A etapa de recuperação de contexto é tão importante quanto o próprio modelo de linguagem. Um LLM avançado não compensa uma base de conhecimento mal estruturada.

---

## 🚀 Aplicação Proposta

Foi projetada uma arquitetura de um sistema corporativo utilizando:

- Python
- LangChain
- RAG
- WhatsApp Business API
- Google Workspace
- Google Calendar
- Banco Vetorial (Milvus ou FAISS)
- Docker
- Kubernetes

### Funcionalidades

- Consulta de documentos corporativos;
- Busca de informações em PDFs e planilhas;
- Agendamento automático de reuniões;
- Consulta de disponibilidade em calendários;
- Respostas contextuais via WhatsApp.

---

## 🏗️ Arquitetura Proposta

```text
Usuário (WhatsApp)
        ↓
Webhook (FastAPI)
        ↓
Agente Orquestrador (LLM)
        ↓
 ┌─────────────────────┐
 │ Ferramentas (Tools) │
 └─────────────────────┘
        ↓
 ┌──────────┬──────────┬──────────┐
 │ RAG Tool │ Calendar │ Workspace│
 └──────────┴──────────┴──────────┘
        ↓
Banco Vetorial + APIs Google
        ↓
Resposta ao Usuário
```

---

## 📚 Miniguia de Estudo

### LLM (Large Language Model)

Modelo de linguagem treinado em grandes volumes de texto para compreender e gerar linguagem natural.

### RAG (Retrieval-Augmented Generation)

Arquitetura que recupera informações externas antes de gerar respostas.

### Embeddings

Representações numéricas que transformam texto em vetores semânticos.

### Banco Vetorial

Sistema responsável por armazenar e recuperar embeddings através de busca por similaridade.

### Chunking

Processo de divisão dos documentos em pequenas partes para indexação.

### Reranker

Componente responsável por reordenar documentos recuperados, priorizando os mais relevantes.

### Guardrails

Mecanismos de segurança para impedir respostas inadequadas ou acesso não autorizado.

---

## 📖 Glossário

| Termo | Definição |
|-------|------------|
| LLM | Large Language Model |
| RAG | Retrieval-Augmented Generation |
| Embedding | Representação vetorial de um texto |
| Vector Database | Banco de dados especializado em vetores |
| Chunk | Pequeno trecho de informação indexado |
| Retrieval | Processo de recuperação de documentos |
| Hallucination | Informação inventada pela IA |
| Top-K | Quantidade de documentos recuperados |
| Reranker | Reordenador de documentos recuperados |
| Guardrails | Camadas de segurança e validação |

---

## 💬 Prompts Reutilizáveis

### Explicação Conceitual

```text
Explique o funcionamento do RAG utilizando exemplos práticos em Python.
```

### Comparação

```text
Compare RAG e Fine-Tuning considerando custo, manutenção e casos de uso.
```

### Arquitetura

```text
Projete uma arquitetura RAG escalável para ambiente corporativo utilizando Python e LLMs.
```

### Troubleshooting

```text
Meu sistema RAG está retornando documentos irrelevantes. Analise possíveis problemas relacionados ao chunking, embeddings, banco vetorial e parâmetros Top-K.
```

### Avaliação

```text
Como medir a qualidade de um sistema RAG utilizando métricas quantitativas e frameworks de avaliação?
```

---

## 🎓 Conclusão

O estudo demonstrou que o RAG vai além de simplesmente conectar um LLM a documentos externos. Sua eficiência depende da qualidade dos dados, estratégias de recuperação, avaliação contínua e mecanismos de segurança.

A realização deste caderno temático permitiu compreender os fundamentos teóricos e visualizar como arquitetar aplicações reais utilizando Python, LLMs e serviços corporativos modernos, aproximando o aprendizado de cenários encontrados no mercado de Inteligência Artificial Generativa.
