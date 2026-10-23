<p align="right"><a href="README.md">🇺🇸 English</a> · 🇧🇷 Português</p>

# Classificação Automática de Mensagens de Erro em Programação

**Utilizando Aprendizado de Máquina para Suporte a Sistemas de Recomendação Educacionais**

Monografia I · Ciência da Computação · Universidade Federal de Ouro Preto (UFOP) · 2026
Orientador: Prof. Reinaldo Silva Fortes

> Este repositório reúne a **primeira etapa do meu Trabalho de Conclusão de Curso (TCC 1)**. Aqui estão os primeiros experimentos e resultados preliminares. A pesquisa continua no **TCC 2**, que aprofunda o trabalho e conclui a graduação.

## Sobre

Mensagens de erro de compiladores costumam ser difíceis de entender para quem está começando a programar, e nem sempre fica claro a qual conteúdo da disciplina o erro está ligado.

Este trabalho desenvolve um modelo que classifica mensagens de erro de programas em C em **sete tópicos de Introdução à Programação**. A ideia é que essa classificação sirva de base para um **sistema de recomendação educacional**, capaz de sugerir conteúdos de estudo de acordo com os erros de cada estudante.

| Classe | Tópico |
|---|---|
| C1 | Tipos de dados, variáveis e constantes |
| C2 | Expressões e operadores |
| C3 | Estruturas condicionais e de repetição |
| C4 | Modularização (funções e procedimentos) |
| C5 | Estruturas de dados homogêneas e heterogêneas |
| C6 | Cadeias de caracteres |
| C7 | Ponteiros e alocação dinâmica de memória |

## Metodologia

- **Dados:** erros de compilação reais de estudantes, adaptados do dataset de *Targeted Example Generation for Compilation Errors* (He et al., 2020). Uma amostra de cerca de 800 mensagens foi rotulada manualmente.
- **Pré-processamento:** extração do primeiro erro reportado pelo compilador Clang e limpeza do texto.
- **Modelo:** Regressão Logística com representação TF-IDF.

Foram comparadas três formas de entrada para o modelo:

| Abordagem | Acurácia |
|---|---|
| Apenas a mensagem de erro | **94%** |
| Mensagem de erro + código-fonte tokenizado | 51% |
| Mensagem de erro + código-fonte original | 66% |

A mensagem de erro sozinha, quando bem tratada, foi a entrada mais informativa. Adicionar o código-fonte trouxe ruído para um modelo linear. As classes com poucos exemplos (C5, C6 e C7) continuam sendo o principal desafio.

## Próximos passos: TCC 2

Os resultados do TCC 1 mostram que a ideia é viável, mas ainda há bastante a avançar. No TCC 2, a proposta é:

- Ampliar o conjunto de dados e tratar o desbalanceamento entre classes.
- Testar modelos mais robustos, como SVM, Random Forest e transformers.
- Integrar a classificação a um sistema de recomendação educacional.

## Notebooks

| Arquivo | Conteúdo |
|---|---|
| `ErrosEcodigos.ipynb` | Extração, limpeza das mensagens e preparação da amostra para rotulação |
| `Classificacao.ipynb` | Abordagem 1: apenas a mensagem de erro |
| `Classificacao_ErrosCodigoLimpo.ipynb` | Abordagem 2: mensagem de erro + código tokenizado |
| `Classificacao_ErrosCodigoOriginal.ipynb` | Abordagem 3: mensagem de erro + código original |

**Tecnologias:** Python · Pandas · scikit-learn · Matplotlib · Seaborn · Google Colab

## Autora

**Mariana Macedo Santos** · [Portfólio](https://marianamacedoo.github.io) · [LinkedIn](https://www.linkedin.com/in/mariana-macedo-7b9ab3227)
