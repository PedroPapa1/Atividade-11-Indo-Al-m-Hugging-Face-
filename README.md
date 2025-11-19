# 🚀 Atividade Prática de Inteligência Artificial: RAG (Retrieval Augmented Generation)

Este repositório contém o código-fonte (em Python/Jupyter Notebook) e a apresentação de slides para a Atividade Avaliativa #11, focada na exploração de tecnologias atuais de Inteligência Artificial e a plataforma **Hugging Face**.

---

## 👥 Integrantes do Grupo

* [**Bruno da Silva**]
* [**Cauã Barchi**]
* [**Gustavo Grassini Calabrez**]
* [**Pedro Henrique Papa**]

---

## 💡 Tópico Escolhido: RAG (Retrieval Augmented Generation)

### O Problema que Queremos Resolver

Grandes Modelos de Linguagem (LLMs), como o GPT ou Gemini, são treinados em um *corpus* de dados até uma data específica. Consequentemente, eles possuem duas grandes limitações:

1.  **Conhecimento Desatualizado:** Não têm acesso a informações pós-treinamento ou dados em tempo real.
2.  **Falta de Conhecimento Privado:** São incapazes de responder perguntas sobre documentos internos, manuais ou dados privados do usuário (o "Projeto Alpha" no nosso exemplo).

### Por Que Escolhemos o RAG?

O RAG é a solução mais eficaz e popular para combater essas limitações. Ele permite que o LLM "consulte" uma base de dados externa (nossa base de conhecimento privada) **antes** de gerar a resposta. Isso garante que as respostas sejam:

* **Precisas:** Baseadas em fontes verificáveis.
* **Confiáveis:** Reduz drasticamente a "alucinação" (tendência do modelo inventar fatos).
* **Contextualizadas:** Adaptadas aos dados específicos do usuário.

---

## 🛠️ Implementação: O Pipeline

Nossa aplicação RAG foi desenvolvida em Python (arquivo `.ipynb`) utilizando o ecossistema Hugging Face, conforme as instruções da atividade.

### Componentes Chave

| Componente | Ferramenta Utilizada | Finalidade |
| :--- | :--- | :--- |
| **Documentos** | Texto Simulado (`knowledge_base`) | A base de conhecimento sobre a qual o LLM deve responder. |
| **Embeddings** | **`sentence-transformers/all-MiniLM-L6-v2`** (Hugging Face) | Transforma o texto em vetores numéricos para busca. |
| **Vector Index** | **FAISS** | Armazena e permite a busca rápida pelos vetores de contexto (o *Retrieval*). |
| **LLM (Geração)** | **`google/flan-t5-small`** (Hugging Face) | O modelo de linguagem que recebe o contexto e gera a resposta final. |

### Fluxo de Execução

1.  O usuário envia uma **Pergunta**.
2.  A pergunta é convertida em um **Vetor**.
3.  O sistema busca os trechos de texto **mais relevantes** no *Vector Index* (Retrieval).
4.  A **Pergunta + Contexto Recuperado** são enviados para o LLM.
5.  O LLM gera a **Resposta Final** baseada no contexto fornecido.

---

## 📂 Conteúdo do Repositório

* `Atividade_11.ipynb`: Notebook Jupyter contendo todo o código Python da aplicação RAG.
* `Atv11PDF.pdf`: Slides em PDF com a explicação do problema, solução e resultados.


