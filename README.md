# Regressão Linear com TensorFlow/Keras

Este projeto demonstra como construir, treinar e usar um modelo simples de **regressão linear** com **TensorFlow/Keras** para prever um valor de saída baseado em um valor de entrada.

## O que o código faz?

1. **Define um modelo de rede neural simples**:
   - Utiliza uma única camada (`Dense`) com um neurônio, que aprende uma relação linear entre as entradas e as saídas.
   - A camada usa a função de erro **mean_squared_error** (erro quadrático médio) para ajustar os parâmetros.

2. **Treina o modelo com dados de entrada (`xs`) e saída (`ys`)**:
   - O conjunto de dados de treino relaciona os valores `xs` e `ys` de forma linear:
     - `xs = [-1.0, 0.0, 1.0, 2.0, 3.0, 4.0]`
     - `ys = [-3.0, -1.0, 1.0, 3.0, 5.0, 7.0]`
   - O modelo aprende a mapear esses valores para identificar o padrão subjacente: **a saída é o dobro da entrada menos um**.

3. **Faz previsões com base em novos dados**:
   - Após o treinamento, o modelo prevê o valor para uma nova entrada, como `10.0`. A saída esperada será algo próximo de `19.0`, já que o modelo aprendeu que a relação é próxima de:
   \[
   y = 2 \cdot x - 1
   \]

## Como o código funciona?

O código segue a seguinte lógica:

1. **Criação do Modelo**:
   - O modelo tem uma única camada com um neurônio, que recebe uma entrada (`xs`) e aprende a prever uma saída (`ys`) aplicando uma função linear simples. O modelo ajusta os **pesos** (multiplicador `w`) e o **viés** (termo constante `b`) para minimizar a diferença entre os valores previstos e os reais.

2. **Treinamento do Modelo**:
   - O modelo é treinado usando o método `fit`, que ajusta os parâmetros internos (peso `w` e viés `b`) por meio da minimização do erro quadrático médio. O treinamento ocorre por 500 épocas, o que significa que o modelo passa pelos dados de treino 500 vezes, refinando os parâmetros a cada iteração.

3. **Previsão**:
   - Após o treinamento, o modelo pode prever o valor de saída para uma nova entrada. Por exemplo, para uma entrada de `10.0`, o modelo aplica a função aprendida \( y = w \cdot x + b \) e retorna algo próximo de `19.0`.

## Por que isso funciona?

O modelo funciona porque os dados de treino (`xs` e `ys`) seguem um padrão linear simples. Durante o treinamento:

- O modelo ajusta o peso `w` (a inclinação da linha) e o viés `b` (o deslocamento da linha) para minimizar a diferença entre os valores de `ys` observados e os previstos.
- No caso dos seus dados, a relação entre `xs` e `ys` pode ser aproximada pela fórmula linear \( y = 2 \cdot x - 1 \).
- Assim, quando fornecemos um novo valor de entrada, como `10.0`, o modelo aplica a equação linear que aprendeu e gera a previsão correspondente (neste caso, `[[18.975584]]`).

Este é um exemplo básico de **regressão linear**, onde o objetivo do modelo é aprender uma função matemática que mapeia entradas para saídas com base em um conjunto de dados de exemplo.

---
