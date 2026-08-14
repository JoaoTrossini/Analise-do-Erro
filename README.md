# Analise-do-Erro
# Atividade Prática - Testes de Software

**Curso:** Técnico em Desenvolvimento de Sistemas
**Professor:** André Denani
**Aluno:** João Trossini
**Data:** 14/08/2026

## Sobre a Atividade

Este repositório contém a atividade prática relacionada aos conceitos de **Testes de Software**, com foco na análise de código, identificação de defeitos, classificação dos tipos de testes e níveis de teste.

A atividade utiliza funções desenvolvidas em Python para simular um sistema de inscrição em um evento, permitindo analisar seu comportamento por meio de testes e identificar possíveis falhas na implementação.

## Objetivos

* Analisar o funcionamento de funções em Python;
* Realizar testes de mesa;
* Identificar erros e defeitos no código;
* Diferenciar testes funcionais e não funcionais;
* Compreender os níveis de teste de software;
* Identificar a importância dos testes durante o desenvolvimento de sistemas.

## Funcionalidades Analisadas

O código apresentado possui três funções principais:

### `validar_inscricao()`

Responsável por verificar se o aluno pode realizar a inscrição, considerando:

* Idade mínima de 16 anos;
* Existência de vagas disponíveis;
* Aprovação ou negação da inscrição.

### `calcular_valor_ingresso()`

Responsável pelo cálculo do valor do ingresso e pela aplicação do cupom de desconto `ALUNO10`.

Durante a análise foi identificado um defeito na implementação: o código subtrai **R$ 10,00 fixos**, em vez de calcular corretamente **10% do valor do ingresso**.

Por exemplo:

* Valor do ingresso: R$ 100,00
* Desconto esperado: 10%
* Desconto: R$ 10,00
* Valor final esperado: R$ 90,00

Apesar de funcionar para um ingresso de R$ 100,00, a lógica apresenta erro para outros valores.

### `realizar_checkout()`

Responsável por realizar o processo completo de inscrição, utilizando as funções de validação e cálculo do ingresso.

Quando a inscrição é permitida, o sistema:

1. Calcula o valor do ingresso;
2. Realiza a inscrição;
3. Reduz a quantidade de vagas disponíveis;
4. Retorna as informações da operação.

Caso a inscrição seja negada, o sistema informa o motivo e mantém a quantidade de vagas.

## Conceitos de Testes Aplicados

### Teste Funcional

A verificação do cupom de desconto é classificada como **teste funcional**, pois verifica se o sistema executa corretamente uma funcionalidade específica.

### Teste de Unidade

O teste da função `validar_inscricao()` de maneira isolada corresponde a um **teste de unidade**, pois apenas uma função é analisada individualmente, sem depender das demais funções do sistema.

## Estrutura do Projeto

```text
/
├── README.md
└── atividade.py
```

## Tecnologias Utilizadas

* **Python**
* **Git**
* **GitHub**
* **VS Code / IDLE**

## Conclusão

A atividade permitiu compreender a importância dos testes de software para identificar defeitos que podem passar despercebidos durante o desenvolvimento.

A análise também demonstrou que um código pode apresentar o resultado correto em determinado cenário e, mesmo assim, possuir uma lógica incorreta. No caso do cupom `ALUNO10`, a implementação funciona para um ingresso de R$ 100,00, mas não aplica corretamente o desconto percentual para outros valores.

Dessa forma, os testes são fundamentais para verificar se o comportamento do sistema está de acordo com os requisitos definidos.
