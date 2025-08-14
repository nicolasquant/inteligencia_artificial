# Classificação de Vinhos com K-Nearest Neighbors (KNN) - Implementação Amanda

## 📋 Descrição do Projeto

Este projeto implementa o algoritmo **K-Nearest Neighbors (KNN)** para classificar vinhos como "bons" ou "ruins" baseando-se em características químicas e físicas. O objetivo é determinar a qualidade do vinho através de análise de 11 atributos diferentes, como acidez, teor alcoólico, pH e outros parâmetros enológicos.

O projeto demonstra os conceitos fundamentais de **aprendizado de máquina supervisionado**, incluindo:
- Implementação manual do algoritmo KNN
- Pré-processamento e normalização de dados
- Divisão em conjuntos de treino e validação
- Cálculo de distâncias euclidianas
- Avaliação de performance do classificador

## 🧠 Explicação Técnica

### Aprendizado de Máquina

**Aprendizado de Máquina** é uma subárea da inteligência artificial que permite aos computadores aprenderem padrões nos dados sem serem explicitamente programados. Neste projeto, utilizamos:

- **Aprendizado Supervisionado**: O algoritmo aprende a partir de exemplos rotulados (vinhos classificados como bons ou ruins)
- **Classificação Binária**: Problema onde o objetivo é classificar vinhos em uma de duas categorias
- **K-Nearest Neighbors (KNN)**: Algoritmo baseado em similaridade que classifica novos dados baseando-se nos K vizinhos mais próximos

### Funcionamento do Algoritmo KNN

1. **Cálculo de Distâncias**:
   - Para cada amostra de validação, calcula a distância euclidiana até todas as amostras de treino
   - Distância euclidiana: `d = √(Σ(x₁-y₁)² + (x₂-y₂)² + ... + (xₙ-yₙ)²)`

2. **Seleção dos K Vizinhos**:
   - Identifica os K pontos de treino mais próximos da amostra de validação
   - K é um hiperparâmetro que determina quantos vizinhos considerar

3. **Classificação por Votação**:
   - Conta a frequência de cada classe entre os K vizinhos mais próximos
   - A classe mais frequente se torna a predição para a nova amostra

### Dataset de Vinhos

O dataset contém informações sobre vinhos com 11 características:
- **Fixed Acidity** (acidez fixa)
- **Volatile Acidity** (acidez volátil)
- **Citric Acid** (ácido cítrico)
- **Residual Sugar** (açúcar residual)
- **Chlorides** (cloretos)
- **Free Sulfur Dioxide** (dióxido de enxofre livre)
- **Total Sulfur Dioxide** (dióxido de enxofre total)
- **Density** (densidade)
- **pH** (potencial hidrogeniônico)
- **Sulphates** (sulfatos)
- **Alcohol** (teor alcoólico)

**Target**: Coluna "is good" indicando se o vinho é bom (1) ou ruim (0).

## ⚙️ Pré-requisitos

Para executar este projeto, você precisará de:

- **Python 3.7+**
- **Jupyter Notebook** ou **Google Colab**
- **Arquivo de dados**: `vinho.csv` (deve estar no mesmo diretório)
- **Conhecimentos básicos** de:
  - Python e Pandas
  - Álgebra linear (cálculo de distâncias)
  - Conceitos fundamentais de machine learning
  - Bibliotecas NumPy e Scikit-learn

## 🚀 Instalação

### Opção 1: Google Colab (Recomendado)
1. Acesse o link do notebook no Google Colab
2. Faça uma cópia para sua conta Google
3. **Importante**: Faça upload do arquivo `vinho.csv` para o Colab
4. Execute as células sequencialmente

### Opção 2: Ambiente Local
1. **Clone o repositório**:
   ```bash
   git clone https://github.com/nicolasquant/inteligencia_artificial.git
   cd inteligencia_artificial
   ```

2. **Instale as dependências**:
   ```bash
   pip install numpy pandas scikit-learn jupyter
   ```

3. **Certifique-se de ter o arquivo `vinho.csv`** no diretório
4. **Execute o Jupyter Notebook**:
   ```bash
   jupyter notebook ML_knn_A.ipynb
   ```

## 📖 Instruções de Uso

### 1. **Preparação dos Dados**
- **Carregamento**: O notebook carrega automaticamente o arquivo `vinho.csv`
- **Exploração**: Use `df.head()` para visualizar as primeiras linhas
- **Verificação**: Confirme que todas as 11 características estão presentes

### 2. **Execução Sequencial**
Execute as células na ordem apresentada:

1. **Importação e carregamento de dados**
2. **Normalização Min-Max** (escala [0,1])
3. **Separação de features e target**
4. **Divisão treino/validação**
5. **Implementação da função de distância**
6. **Classe KNN personalizada**
7. **Treinamento e predição**
8. **Avaliação da performance**

### 3. **Parâmetros Configuráveis**
- **`test_size = 0.2`**: Proporção de dados para validação (20%)
- **`random_state = 42`**: Semente para reprodutibilidade
- **`k`**: Número de vizinhos (hiperparâmetro principal)
- **Função de normalização**: Min-Max Scaling para escala [0,1]

### 4. **Implementação da Classe KNN**
A classe implementa três métodos principais:
- **`__init__(self, k)`**: Inicializa com o número de vizinhos
- **`fit(self, X, y)`**: Armazena os dados de treino
- **`predict(self, X_val)`**: Classifica novas amostras

### 5. **Interpretação dos Resultados**
- **Taxa de acerto**: Porcentagem de predições corretas
- **Matriz de confusão**: Detalhamento de acertos e erros
- **Influência do parâmetro K**: Como o número de vizinhos afeta a performance

### 6. **Personalizações Possíveis**
- Testar diferentes valores de K
- Implementar outras métricas de distância (Manhattan, Minkowski)
- Adicionar validação cruzada
- Implementar ponderação por distância
- Testar diferentes técnicas de normalização

## 🔍 Estrutura do Código

```
├── Importação de bibliotecas
├── Carregamento do dataset de vinhos
├── Normalização Min-Max dos dados
├── Separação de features e target
├── Divisão treino/validação
├── Implementação da função de distância
├── Classe KNN personalizada
├── Treinamento e predição
└── Avaliação da performance
```

## 📊 Resultados Esperados

Após a execução, você verá:
- Dataset normalizado com valores entre 0 e 1
- Taxa de acerto do classificador KNN
- Comparação entre valores reais e preditos
- Análise da influência do parâmetro K na performance

## 🎯 Aplicações Práticas

Este projeto serve como base para:
- Entender algoritmos baseados em similaridade
- Implementar classificadores KNN do zero
- Aprender sobre pré-processamento de dados
- Aplicar machine learning em problemas de classificação
- Entender a importância da normalização de dados

## ⚠️ Considerações Importantes

- **Arquivo de dados**: Certifique-se de ter o arquivo `vinho.csv`
- **Normalização**: Dados devem estar na mesma escala para cálculo correto de distâncias
- **Parâmetro K**: Valores muito baixos podem causar overfitting, valores muito altos podem causar underfitting
- **Performance**: KNN pode ser computacionalmente custoso para datasets grandes

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para:
- Reportar bugs
- Sugerir melhorias
- Adicionar novas funcionalidades
- Melhorar a documentação

## 📚 Referências

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [Pandas Documentation](https://pandas.pydata.org/)
- [NumPy Documentation](https://numpy.org/)
- [K-Nearest Neighbors Algorithm](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm)

---

**Desenvolvido por**: Amanda (Colaboração com Nicolas Quant)  
**Data**: 2024  
**Licença**: MIT
