# Implementação do Algoritmo K-Means para Clustering - Dataset Iris

## 📋 Descrição do Projeto

Este projeto implementa o algoritmo **K-Means** do zero para realizar **clustering** (agrupamento) de dados no dataset Iris. O objetivo é agrupar as flores em 3 clusters baseando-se nas características das pétalas (comprimento e largura), demonstrando como o algoritmo identifica padrões e organiza dados similares em grupos.

O projeto demonstra os conceitos fundamentais de **aprendizado de máquina não supervisionado**, incluindo:
- Implementação manual do algoritmo K-Means
- Seleção de centroides iniciais aleatórios
- Cálculo de distâncias euclidianas
- Atualização iterativa de centroides
- Avaliação de qualidade através de variância
- Visualização de clusters e centroides

## 🧠 Explicação Técnica

### Aprendizado de Máquina

**Aprendizado de Máquina** é uma subárea da inteligência artificial que permite aos computadores aprenderem padrões nos dados sem serem explicitamente programados. Neste projeto, utilizamos:

- **Aprendizado Não Supervisionado**: O algoritmo descobre padrões nos dados sem rótulos pré-definidos
- **Clustering**: Técnica para agrupar dados similares em clusters
- **K-Means**: Algoritmo iterativo que minimiza a variância dentro de cada cluster
- **Análise Exploratória**: Descoberta de estrutura nos dados

### Funcionamento do Algoritmo K-Means

1. **Inicialização**:
   - Define o número de clusters (K = 3)
   - Seleciona K pontos aleatórios como centroides iniciais
   - Utiliza características das pétalas (comprimento e largura)

2. **Atribuição de Pontos**:
   - Calcula distância euclidiana de cada ponto aos centroides
   - Atribui cada ponto ao cluster do centroide mais próximo
   - Formula: `d = √((x₁-y₁)² + (x₂-y₂)²)`

3. **Atualização de Centroides**:
   - Calcula a média de todos os pontos em cada cluster
   - Move o centroide para a nova posição média
   - Repete até convergência ou número máximo de iterações

4. **Avaliação de Qualidade**:
   - Calcula variância dentro de cada cluster
   - Soma total das variâncias como métrica de qualidade
   - Menor variância total indica melhor agrupamento

### Dataset Iris

O dataset contém 150 amostras de flores com 4 características:
- **Sepal Length** (comprimento da sépala)
- **Sepal Width** (largura da sépala)
- **Petal Length** (comprimento da pétala) ← **Utilizado**
- **Petal Width** (largura da pétala) ← **Utilizado**

Para este projeto, utilizamos apenas as características das **pétalas** (colunas 2 e 3) para facilitar a visualização 2D.

## ⚙️ Pré-requisitos

Para executar este projeto, você precisará de:

- **Python 3.7+**
- **Jupyter Notebook** ou **Google Colab**
- **Conhecimentos básicos** de:
  - Python e NumPy
  - Álgebra linear (cálculo de distâncias, médias)
  - Conceitos fundamentais de machine learning
  - Bibliotecas Matplotlib e Scikit-learn
  - Algoritmos de ordenação (QuickSort)

## 🚀 Instalação

### Opção 1: Google Colab (Recomendado)
1. Acesse o link do notebook no Google Colab
2. Faça uma cópia para sua conta Google
3. Execute as células sequencialmente

### Opção 2: Ambiente Local
1. **Clone o repositório**:
   ```bash
   git clone https://github.com/nicolasquant/inteligencia_artificial.git
   cd inteligencia_artificial
   ```

2. **Instale as dependências**:
   ```bash
   pip install numpy matplotlib scikit-learn jupyter
   ```

3. **Execute o Jupyter Notebook**:
   ```bash
   jupyter notebook kmeans.ipynb
   ```

## 📖 Instruções de Uso

### 1. **Estrutura do Notebook**
O notebook está organizado em seções lógicas:

- **Importação e preparação de dados**
- **Implementação do QuickSort**
- **Implementação do K-Means**
- **Execução e avaliação**
- **Visualização dos resultados**

### 2. **Execução Sequencial**
Execute as células na ordem apresentada:

1. **Importação de bibliotecas e carregamento de dados**
2. **Implementação do algoritmo QuickSort** (para ordenação)
3. **Pré-processamento dos dados** (divisão treino/teste, normalização)
4. **Visualização inicial** dos dados com classes reais
5. **Implementação das funções auxiliares**:
   - `random_points()`: Seleção aleatória de centroides
   - `distancia_euclidiana()`: Cálculo de distância entre pontos
6. **Execução do K-Means** com múltiplas inicializações
7. **Seleção da melhor solução** baseada na variância
8. **Visualização final** dos clusters e centroides

### 3. **Parâmetros Configuráveis**
- **`k = 3`**: Número de clusters (classes de flores)
- **`test_size = 0.2`**: Proporção de dados para teste (20%)
- **`random_state = 42`**: Semente para reprodutibilidade
- **`10`**: Número de inicializações aleatórias para encontrar melhor solução

### 4. **Implementação das Funções**

#### QuickSort para Ordenação
```python
def quicksort(arr, left, right):
    if left < right:
        partition_pos = partition(arr, left, right)
        quicksort(arr, left, partition_pos - 1)
        quicksort(arr, partition_pos + 1, right)
```

#### Seleção de Centroides Aleatórios
```python
def random_points(matriz_de_dados, k):
    pontos = []
    for i in range(k):
        coordenada = int(len(matriz_de_dados)*np.random.random())
        pontos.append(matriz_de_dados[coordenada])
    return pontos
```

#### Cálculo de Distância Euclidiana
```python
def distancia_euclidiana(ponto1, ponto2):
    x = ponto1[0] - ponto2[0]
    y = ponto1[1] - ponto2[1]
    return np.sqrt(x**2 + y**2)
```

### 5. **Processo de Otimização**
1. **Múltiplas Inicializações**: Gera 10 conjuntos diferentes de centroides aleatórios
2. **Execução do K-Means**: Para cada inicialização, executa o algoritmo completo
3. **Cálculo de Variância**: Mede a qualidade de cada agrupamento
4. **Seleção da Melhor Solução**: Escolhe a inicialização com menor variância total
5. **Re-execução**: Aplica o K-Means com os melhores centroides iniciais

### 6. **Interpretação dos Resultados**
- **Gráficos de dispersão**: Mostram a distribuição dos pontos por cluster
- **Centroides**: Pontos médios de cada cluster (marcados com cores diferentes)
- **Qualidade do agrupamento**: Avaliada pela variância total dos clusters
- **Comparação**: Visualização dos dados reais vs. clusters encontrados

### 7. **Personalizações Possíveis**
- Alterar o número de clusters (K)
- Modificar o número de inicializações aleatórias
- Implementar critérios de parada mais sofisticados
- Adicionar outras métricas de qualidade (Silhouette Score, Inertia)
- Testar diferentes métodos de inicialização (K-Means++)

## 🔍 Estrutura do Código

```
├── Importação de bibliotecas
├── Implementação do QuickSort
├── Carregamento do dataset Iris
├── Seleção de características (pétalas)
├── Divisão treino/teste
├── Normalização dos dados
├── Visualização inicial
├── Implementação das funções auxiliares
├── Execução do K-Means (múltiplas inicializações)
├── Seleção da melhor solução
├── Re-execução com melhores centroides
└── Visualização final dos resultados
```

## 📊 Resultados Esperados

Após a execução, você verá:
- Gráfico inicial mostrando as 3 classes reais do dataset
- Gráfico final mostrando os 3 clusters encontrados pelo K-Means
- Centroides de cada cluster marcados com cores diferentes
- Comparação entre agrupamento real e agrupamento aprendido
- Métricas de qualidade baseadas na variância dos clusters

## 🎯 Aplicações Práticas

Este projeto serve como base para:
- Entender algoritmos de clustering não supervisionado
- Implementar K-Means do zero
- Aprender sobre inicialização de centroides
- Visualizar o processo de agrupamento
- Aplicar conceitos em problemas reais de segmentação
- Entender a importância da inicialização em algoritmos iterativos

## ⚠️ Considerações Importantes

- **Inicialização Aleatória**: Diferentes execuções podem produzir resultados diferentes
- **Convergência Local**: O algoritmo pode convergir para mínimos locais
- **Escolha de K**: O número de clusters deve ser conhecido a priori
- **Escala dos Dados**: Normalização é importante para distâncias euclidianas
- **Múltiplas Execuções**: Executar várias vezes ajuda a encontrar melhor solução

## 🔍 Características Especiais

Esta implementação se destaca por:
- **Implementação Manual**: Algoritmo desenvolvido do zero para aprendizado
- **Múltiplas Inicializações**: 10 execuções para encontrar melhor solução
- **Avaliação por Variância**: Métrica simples mas efetiva para qualidade
- **QuickSort Personalizado**: Algoritmo de ordenação implementado manualmente
- **Visualização Completa**: Gráficos antes e depois do clustering

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para:
- Reportar bugs
- Sugerir melhorias
- Adicionar novas funcionalidades
- Melhorar a documentação
- Implementar outras métricas de avaliação

## 📚 Referências

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [NumPy Documentation](https://numpy.org/)
- [Matplotlib Documentation](https://matplotlib.org/)
- [Dataset Iris - UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/iris)
- [K-Means Clustering Algorithm](https://en.wikipedia.org/wiki/K-means_clustering)

---

**Desenvolvido por**: Nicolas Quant  
**Data**: 2024  
**Licença**: MIT
