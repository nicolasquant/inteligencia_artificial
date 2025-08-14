# Classificação Binária com Dataset Iris - Perceptron Simples

## 📋 Descrição do Projeto

Este projeto implementa um algoritmo de **classificação binária** utilizando um **perceptron simples** para classificar flores do dataset Iris. O objetivo é distinguir entre duas espécies específicas de Iris (Setosa e Virginica) baseando-se em características morfológicas das flores, como comprimento e largura das sépalas e pétalas.

O projeto demonstra os conceitos fundamentais de **aprendizado de máquina supervisionado**, incluindo:
- Pré-processamento de dados
- Divisão em conjuntos de treino e teste
- Normalização de características
- Implementação de um perceptron com função de ativação sigmóide
- Algoritmo de backpropagation para treinamento
- Visualização de resultados e fronteiras de decisão

## 🧠 Explicação Técnica

### Aprendizado de Máquina

**Aprendizado de Máquina** é um subcampo da inteligência artificial que permite aos computadores aprenderem padrões nos dados sem serem explicitamente programados para cada tarefa específica. Neste projeto, utilizamos:

- **Aprendizado Supervisionado**: O algoritmo aprende a partir de exemplos rotulados (dados de entrada com suas respectivas saídas corretas)
- **Classificação Binária**: Problema onde o objetivo é classificar dados em uma de duas categorias possíveis
- **Perceptron**: O modelo mais simples de rede neural, capaz de aprender funções linearmente separáveis

### Funcionamento do Algoritmo

1. **Forward Pass**: 
   - Combinação linear das entradas com pesos: `z = X·w + b`
   - Aplicação da função sigmóide: `σ(z) = 1/(1 + e^(-z))`
   - Geração da predição: `y_pred = σ(z)`

2. **Backpropagation**:
   - Cálculo do erro: `error = y_pred - y_true`
   - Atualização dos pesos: `w = w - α·∇w`
   - Atualização do bias: `b = b - α·∇b`

3. **Função de Ativação Sigmóide**:
   - Transforma qualquer valor real em um valor entre 0 e 1
   - Permite interpretar a saída como uma probabilidade
   - Suaviza as transições e facilita o cálculo das derivadas

### Dataset Iris

O dataset Iris contém 150 amostras de flores com 4 características:
- **Sepal Length** (comprimento da sépala)
- **Sepal Width** (largura da sépala)  
- **Petal Length** (comprimento da pétala)
- **Petal Width** (largura da pétala)

Para este projeto binário, filtramos apenas as classes **Iris Setosa** (classe 0) e **Iris Virginica** (classe 2, recodificada como 1).

## ⚙️ Pré-requisitos

Para executar este projeto, você precisará de:

- **Python 3.7+**
- **Jupyter Notebook** ou **Google Colab**
- **Conhecimentos básicos** de:
  - Python
  - Álgebra linear
  - Conceitos fundamentais de machine learning
  - Bibliotecas NumPy e Matplotlib

## 🚀 Instalação

### Opção 1: Google Colab (Recomendado para iniciantes)
1. Acesse o link do notebook no Google Colab
2. Faça uma cópia para sua conta Google
3. Execute as células sequencialmente

### Opção 2: Ambiente Local
1. **Clone o repositório**:
   ```bash
   git clone https://github.com/nicolasquant/inteligencia_artificial.git
   cd inteligencia_artificial/AM_classificacao_supervisionada
   ```

2. **Instale as dependências**:
   ```bash
   pip install numpy matplotlib scikit-learn jupyter
   ```

3. **Execute o Jupyter Notebook**:
   ```bash
   jupyter notebook Iris_Dataset_binario.ipynb
   ```

## 📖 Instruções de Uso

### 1. **Execução Sequencial**
Execute as células do notebook na ordem apresentada:
- **Célula 1**: Importação das bibliotecas
- **Célula 2**: Carregamento e preparação dos dados
- **Célula 3**: Normalização dos dados
- **Célula 4**: Visualização dos dados
- **Célula 5**: Inicialização dos pesos e bias
- **Célula 6**: Definição das funções auxiliares
- **Célula 7**: Visualização inicial das fronteiras de decisão
- **Célula 8**: Implementação do algoritmo de treinamento
- **Célula 9**: Treinamento do modelo
- **Célula 10**: Visualização final das fronteiras de decisão

### 2. **Parâmetros Configuráveis**
- **`test_size=0.2`**: Proporção de dados para teste (20%)
- **`random_state=42`**: Semente para reprodutibilidade
- **`learning_rate=0.005`**: Taxa de aprendizado
- **`100`**: Número de épocas de treinamento

### 3. **Interpretação dos Resultados**
- **Gráficos de dispersão**: Mostram a distribuição das classes
- **Fronteiras de decisão**: Visualizam como o modelo classifica os dados
- **Curvas de aprendizado**: Monitoram a acurácia e MSE durante o treinamento
- **Pesos finais**: Representam o modelo treinado

### 4. **Personalizações Possíveis**
- Alterar a taxa de aprendizado
- Modificar o número de épocas
- Testar diferentes funções de ativação
- Implementar validação cruzada
- Adicionar regularização

## 🔍 Estrutura do Código

```
├── Importação de bibliotecas
├── Carregamento do dataset Iris
├── Filtragem para classificação binária
├── Divisão treino/teste
├── Normalização dos dados
├── Visualização inicial
├── Inicialização dos parâmetros
├── Definição das funções
├── Treinamento do modelo
└── Avaliação e visualização
```

## 📊 Resultados Esperados

Após a execução, você verá:
- Gráficos mostrando a separação das duas classes
- Fronteiras de decisão que se ajustam durante o treinamento
- Curvas de aprendizado mostrando a evolução da acurácia
- Modelo treinado capaz de classificar novas amostras

## 🎯 Aplicações Práticas

Este projeto serve como base para:
- Entender algoritmos de classificação
- Implementar perceptrons simples
- Aprender sobre backpropagation
- Visualizar o processo de aprendizado
- Aplicar conceitos em problemas reais de classificação

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para:
- Reportar bugs
- Sugerir melhorias
- Adicionar novas funcionalidades
- Melhorar a documentação

## 📚 Referências

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [NumPy Documentation](https://numpy.org/)
- [Matplotlib Documentation](https://matplotlib.org/)
- [Dataset Iris - UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/iris)

---

**Desenvolvido por**: Nicolas Quant  
**Data**: 2024  
**Licença**: MIT
