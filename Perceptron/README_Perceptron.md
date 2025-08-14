# Implementação de Perceptron para Classificação Binária - Dataset Iris

## 📋 Descrição do Projeto

Este projeto implementa um **perceptron simples** do zero para realizar classificação binária no dataset Iris. O objetivo é distinguir entre duas espécies específicas de flores Iris (Setosa e Virginica) utilizando características morfológicas como comprimento e largura das sépalas e pétalas.

O projeto demonstra os conceitos fundamentais de **redes neurais artificiais**, incluindo:
- Implementação manual de um perceptron
- Função de ativação sigmóide
- Algoritmo de treinamento iterativo
- Visualização de fronteiras de decisão
- Pré-processamento e normalização de dados

## 🧠 Explicação Técnica

### Aprendizado de Máquina

**Aprendizado de Máquina** é uma subárea da inteligência artificial que permite aos computadores aprenderem padrões nos dados sem serem explicitamente programados. Neste projeto, utilizamos:

- **Aprendizado Supervisionado**: O algoritmo aprende a partir de exemplos rotulados
- **Classificação Binária**: Problema onde o objetivo é classificar dados em uma de duas categorias
- **Perceptron**: O modelo mais simples de rede neural, capaz de aprender funções linearmente separáveis

### Funcionamento do Perceptron

1. **Entrada e Pesos**:
   - Dados de entrada: características das flores (4 dimensões)
   - Pesos: valores aleatórios inicializados para cada característica
   - Bias: termo constante para ajustar a função de decisão

2. **Cálculo da Saída**:
   - Combinação linear: `Z = X·W + b`
   - Função de ativação sigmóide: `σ(Z) = 1/(1 + e^(-Z))`
   - Saída: valor entre 0 e 1 representando a probabilidade da classe

3. **Treinamento**:
   - Comparação entre saída prevista e valor real
   - Ajuste iterativo dos pesos e bias
   - Convergência para uma solução ótima

### Dataset Iris

O dataset contém 150 amostras com 4 características:
- **Sepal Length** (comprimento da sépala)
- **Sepal Width** (largura da sépala)
- **Petal Length** (comprimento da pétala)
- **Petal Width** (largura da pétala)

Para classificação binária, filtramos apenas **Iris Setosa** (classe 0) e **Iris Virginica** (classe 2, recodificada como 1).

## ⚙️ Pré-requisitos

Para executar este projeto, você precisará de:

- **Python 3.7+**
- **Jupyter Notebook** ou **Google Colab**
- **Conhecimentos básicos** de:
  - Python e NumPy
  - Álgebra linear (produto escalar, matrizes)
  - Conceitos fundamentais de machine learning
  - Bibliotecas Matplotlib e Scikit-learn

## 🚀 Instalação

### Opção 1: Google Colab (Recomendado)
1. Acesse o link do notebook no Google Colab
2. Faça uma cópia para sua conta Google
3. Execute as células sequencialmente

### Opção 2: Ambiente Local
1. **Clone o repositório**:
   ```bash
   git clone https://github.com/nicolasquant/inteligencia_artificial.git
   cd inteligencia_artificial/Perceptron
   ```

2. **Instale as dependências**:
   ```bash
   pip install numpy matplotlib scikit-learn jupyter
   ```

3. **Execute o Jupyter Notebook**:
   ```bash
   jupyter notebook Perceptron.ipynb
   ```

## 📖 Instruções de Uso

### 1. **Estrutura do Notebook**
O notebook está organizado em seções lógicas:

- **PARTE 0**: Tratamento e preparação dos dados
- **PARTE 1**: Implementação das funções do perceptron
- **PARTE 2**: Treinamento e visualização do modelo

### 2. **Execução Sequencial**
Execute as células na ordem apresentada:

1. **Importação e carregamento de dados**
2. **Pré-processamento** (filtragem, divisão treino/teste, normalização)
3. **Inicialização dos parâmetros** (pesos e bias)
4. **Implementação das funções** (cálculo de Z, função sigmóide)
5. **Função de visualização** (fronteiras de decisão)
6. **Treinamento do modelo**
7. **Avaliação e visualização dos resultados**

### 3. **Parâmetros Configuráveis**
- **`eta = 0.01`**: Coeficiente de aprendizado
- **`test_size = 0.2`**: Proporção de dados para teste
- **`random_state = 42`**: Semente para reprodutibilidade
- **Número de iterações**: Ajustável conforme necessário

### 4. **Interpretação dos Resultados**
- **Gráficos de dispersão**: Mostram a distribuição das classes
- **Fronteiras de decisão**: Visualizam como o perceptron classifica os dados
- **Pesos finais**: Representam o modelo treinado
- **Acurácia**: Medida de performance do classificador

### 5. **Personalizações Possíveis**
- Alterar a taxa de aprendizado
- Modificar o número de iterações
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
├── Inicialização dos parâmetros
├── Implementação das funções
├── Treinamento do modelo
└── Visualização dos resultados
```

## 📊 Resultados Esperados

Após a execução, você verá:
- Gráficos mostrando a separação das duas classes
- Fronteiras de decisão que se ajustam durante o treinamento
- Modelo treinado capaz de classificar novas amostras
- Pesos finais que representam a solução aprendida

## 🎯 Aplicações Práticas

Este projeto serve como base para:
- Entender o funcionamento básico de redes neurais
- Implementar algoritmos de classificação simples
- Aprender sobre pré-processamento de dados
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
