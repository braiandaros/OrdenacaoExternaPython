# 🧮 Ordenação Externa --- Intercalação Balanceada de 3 Caminhos

Este projeto implementa o algoritmo de **Ordenação Externa** utilizando
o método de **Intercalação Balanceada de 3 Caminhos** (*3-way Multi-way
Merge Sort*).\
O trabalho foi desenvolvido como parte da disciplina **Estrutura de
Dados II**.

## 📘 Objetivo

Ordenar um arquivo contendo uma grande quantidade de números inteiros,
simulando um cenário onde o volume de dados **excede a memória
principal**.\
Para isso, são utilizadas **fitas auxiliares** e um **buffer interno
limitado a 3 registros**.

## ⚙️ Regras e restrições do algoritmo

-   **Método:** Intercalação Balanceada de 3 Caminhos\
-   **Memória interna (buffer):** `M = 3` registros\
-   **Fitas auxiliares:** 6 fitas no total
    -   3 fitas de entrada\
    -   3 fitas de saída\
-   **Estruturas:** Buffers manuais de leitura, escrita e controle de
    blocos\
-   **Entrada:** arquivo `entrada.txt` contendo inteiros (um por linha)

## 🚀 Funcionamento do Algoritmo

O processo é dividido em **duas fases principais**:

### 🔹 1. Fase de Distribuição (Geração dos Blocos Iniciais)

1.  O arquivo `entrada.txt` é lido em blocos de tamanho `M` (3 números
    por vez).\
2.  Cada bloco é ordenado internamente no buffer.\
3.  Os blocos ordenados são distribuídos **ciclicamente** entre as 3
    fitas de saída.

### 🔹 2. Fase de Intercalação (Merge Balanceado)

1.  Três blocos --- um de cada fita de entrada --- são lidos
    simultaneamente.\
2.  É realizada a **intercalação de 3 caminhos** (merge 3-way).\
3.  O resultado é escrito nas 3 fitas de saída, formando blocos maiores
    a cada passada.\
4.  Ao final de cada passada:
    -   as **fitas de entrada viram saída**,\
    -   e as **fitas de saída viram entrada**.

O processo continua até restar **um único bloco ordenado** contendo
todos os números.

## 🛠️ Estrutura do Código

-   `fase_1_distribuicao()`: Lê blocos iniciais, ordena e distribui nas
    fitas.\
-   `fase_2_intercalacao()`: Controla as passadas do merge e alternância
    das fitas.\
-   `sort_com_fitas()`: Ordenação interna com rastreabilidade.\
-   `ordenar_arquivo_externo()`: Função principal que orquestra tudo.

## 📦 Como Executar

### ▶️ Passo a passo

1.  Clone o repositório:

    ``` bash
    git clone https://github.com/seu-usuario/nome-do-repositorio.git
    ```

2.  Acesse a pasta do projeto:

    ``` bash
    cd nome-do-repositorio
    ```

3.  Certifique-se de que existe um arquivo `entrada.txt` com números
    inteiros.\

4.  Execute o script:

    ``` bash
    python AOP3_SeuNome.py
    ```

## 🔍 Exemplo de Resultado

Entrada:

    8
    3
    12
    1
    4
    7

Saída:

    1
    3
    4
    7
    8
    12

## ✨ Possíveis Melhorias

-   Tornar `M` configurável\
-   Suporte a k-way merge genérico\
-   Logs e testes automatizados
