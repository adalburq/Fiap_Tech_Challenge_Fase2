# Fine-Tuning do Modelo LLaMA 3.2 3B com LoRA para Suporte ao Diagnóstico de Diabetes

## Resumo
Este projeto apresenta o desenvolvimento de um pipeline de *fine-tuning* aplicado ao modelo **LLaMA 3.2 3B** utilizando a técnica **LoRA (Low-Rank Adaptation)**.  
O objetivo é construir um assistente clínico capaz de interpretar saídas de modelos de *Machine Learning* voltados ao diagnóstico de diabetes, fornecendo explicações humanizadas e alinhadas às diretrizes médicas.  

Para otimização do modelo de classificação, foi empregado um **algoritmo genético**, resultando em melhorias significativas no *recall* e redução de falsos negativos.

A infraestrutura utiliza ferramentas open source como **MLflow, Docker e ngrok**, garantindo observabilidade, reprodutibilidade e escalabilidade.  
Os resultados demonstram a viabilidade da aplicação de LLMs ajustadas para suporte à decisão clínica.

---

## Objetivos

### Objetivo Geral
Desenvolver um modelo de linguagem ajustado capaz de interpretar resultados de modelos preditivos de diabetes e gerar explicações clínicas contextualizadas.  

### Objetivos Específicos
- Aplicar *fine-tuning* em uma LLM utilizando LoRA  
- Reduzir custo computacional com QLoRA  
- Melhorar desempenho de classificação com algoritmo genético  
- Implementar monitoramento com MLflow  
- Garantir consistência entre probabilidade e classificação  

---

## Referencial Teórico
- **Modelos de Linguagem de Grande Porte**: LLaMA e outros modelos são amplamente utilizados em tarefas de NLP.  
- **LoRA**: Técnica que permite adaptar modelos treinando apenas um subconjunto de parâmetros, reduzindo custo computacional.  
- **Algoritmos Genéticos**: Métodos de otimização inspirados na seleção natural, aplicados em espaços de busca complexos.  

---

## Metodologia

### Dataset
- **Fonte**: Pima Indians Diabetes Database (UCI Machine Learning Repository)  
- **Formato**: JSONL contendo classificação, probabilidade, fatores clínicos e dados do paciente  
- **Divisão**:
  - Treino: 3000 amostras  
  - Validação: 600 amostras  
  - Teste: 300 amostras  

### Pipeline
1. Preparação do ambiente  
2. Carregamento de dados  
3. Configuração do modelo  
4. Fine-tuning com LoRA  
5. Avaliação  
6. Inferência  

### Ferramentas
- Transformers (Hugging Face)  
- PEFT (LoRA)  
- TRL (SFTTrainer)  
- MLflow  
- Docker  
- ngrok  

---

## Implementação

### Modelo Base
- LLaMA 3.2 3B com quantização 4-bit (QLoRA)  

### Configuração LoRA
- Rank (r): 32  
- Alpha: 64  
- Dropout: 0.10  

### Treinamento
- Learning rate: 1e-4  
- Scheduler: cosine  
- Early stopping  

### Monitoramento
- Registro de métricas e versionamento com MLflow  
- Isolamento do ambiente com Docker  
- Acesso remoto via ngrok  

---

## Resultados

### Modelo Original
- Recall: 0.50  
- Falsos negativos: 27  

### Modelo Otimizado (com algoritmo genético)
- Recall: 0.81  
- Falsos negativos: 10  

Observou-se redução significativa de erros críticos, fundamental em aplicações médicas.  

---

## Discussão
A combinação entre algoritmos genéticos e *fine-tuning* de LLMs mostrou-se eficaz para suporte à decisão clínica.  
O aumento de falsos positivos foi considerado aceitável, dado o contexto médico, onde a prioridade é minimizar riscos ao paciente.  

---

## Conclusão
Este trabalho demonstrou a eficácia da aplicação de técnicas modernas de *fine-tuning* em modelos de linguagem para a área da saúde.  

- LoRA reduziu significativamente o custo computacional.  
- Algoritmo genético melhorou o desempenho preditivo.  
- Infraestrutura baseada em ferramentas open source garantiu escalabilidade e observabilidade.  

### Trabalhos Futuros
- Expansão do dataset  
- Integração com sistemas hospitalares  
- Validação com especialistas da área médica  

---

## Referências
- UCI Machine Learning Repository – Pima Indians Diabetes Database  
- Hugging Face – Transformers Documentation  
- Microsoft – LoRA: Low-Rank Adaptation of Large Language Models  
- MLflow Documentation  
