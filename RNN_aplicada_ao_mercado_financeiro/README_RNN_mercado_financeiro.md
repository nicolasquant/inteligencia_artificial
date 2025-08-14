# Previsão Temporal no Mercado Financeiro com Redes Neurais - TensorFlow

## 📋 Descrição do Projeto

Este projeto implementa um sistema de **previsão temporal** para o mercado financeiro utilizando **redes neurais artificiais** com TensorFlow. O objetivo é prever movimentos de preços de ações e implementar uma estratégia de trading automatizada baseada em análise de séries temporais.

O projeto demonstra conceitos avançados de **aprendizado de máquina e deep learning**, incluindo:
- Análise de séries temporais financeiras
- Implementação de redes neurais densas
- Estratégia de trading automatizada
- Gestão de portfólio baseada em predições
- Normalização e pré-processamento de dados financeiros

## 🧠 Explicação Técnica

### Aprendizado de Máquina

**Aprendizado de Máquina** é uma subárea da inteligência artificial que permite aos computadores aprenderem padrões nos dados sem serem explicitamente programados. Neste projeto, utilizamos:

- **Aprendizado Supervisionado**: O algoritmo aprende a partir de dados históricos de preços
- **Regressão Temporal**: Problema onde o objetivo é prever valores futuros baseado em padrões passados
- **Deep Learning**: Redes neurais com múltiplas camadas para capturar padrões complexos
- **Transfer Learning**: Reutilização de modelos treinados para diferentes ativos

### Funcionamento do Sistema

1. **Análise de Janela Temporal**:
   - Utiliza os últimos 7 dias de dados para fazer predições
   - Janela deslizante que se move a cada dia de trading
   - Adaptação contínua do modelo aos novos dados

2. **Arquitetura da Rede Neural**:
   - **Camada de Normalização**: Padroniza os dados de entrada
   - **Camada Densa**: Aprende padrões lineares e não-lineares
   - **Otimizador Adam**: Algoritmo de otimização adaptativo
   - **Função de Perda**: Mean Absolute Error (MAE)

3. **Estratégia de Trading**:
   - **Análise de Tendência**: Identifica se o preço está subindo ou descendo
   - **Sinal de Compra**: Quando a predição indica alta futura
   - **Sinal de Venda**: Quando a predição indica baixa futura
   - **Gestão de Risco**: Controle de posições e capital

### Dataset Financeiro

O sistema trabalha com dados de ações brasileiras contendo:
- **Preços históricos**: Valores de fechamento diários
- **Múltiplos ativos**: Até 25 ações diferentes simultaneamente
- **Séries temporais**: Dados organizados cronologicamente
- **Divisão temporal**: 70% para treino, 30% para teste

**Estrutura dos dados**:
- **Linhas**: Dias de trading
- **Colunas**: Diferentes ativos (ações)
- **Valores**: Preços de fechamento das ações

## ⚙️ Pré-requisitos

Para executar este projeto, você precisará de:

- **Python 3.8+**
- **Jupyter Notebook** ou **Google Colab**
- **Arquivo de dados**: `Data_trat.csv` (dados financeiros tratados)
- **Conhecimentos avançados** de:
  - Python e Pandas
  - TensorFlow/Keras
  - Análise de séries temporais
  - Conceitos de mercado financeiro
  - Redes neurais e deep learning

## 🚀 Instalação

### Opção 1: Google Colab (Recomendado)
1. Acesse o link do notebook no Google Colab
2. Faça uma cópia para sua conta Google
3. **Importante**: Faça upload do arquivo `Data_trat.csv` para o Colab
4. Execute as células sequencialmente

### Opção 2: Ambiente Local
1. **Clone o repositório**:
   ```bash
   git clone https://github.com/nicolasquant/inteligencia_artificial.git
   cd inteligencia_artificial/RNN_aplicada_ao_mercado_financeiro
   ```

2. **Instale as dependências**:
   ```bash
   pip install tensorflow pandas numpy matplotlib jupyter
   ```

3. **Certifique-se de ter o arquivo `Data_trat.csv`** no diretório
4. **Execute o Jupyter Notebook**:
   ```bash
   jupyter notebook main_previsao_temporal_tensorflow.ipynb
   ```

## 📖 Instruções de Uso

### 1. **Preparação dos Dados**
- **Carregamento**: O notebook carrega automaticamente o arquivo `Data_trat.csv`
- **Verificação**: Confirme que os dados estão organizados por data (linhas) e ativos (colunas)
- **Limpeza**: Remoção automática de ativos com valores zero

### 2. **Execução Sequencial**
Execute as células na ordem apresentada:

1. **Importação de bibliotecas e dados**
2. **Configuração de parâmetros** (janela temporal, dias de teste)
3. **Pré-processamento dos dados**
4. **Loop principal de trading**:
   - Treinamento dos modelos para cada ativo
   - Predição de preços futuros
   - Execução de estratégias de compra/venda
   - Atualização do portfólio

### 3. **Parâmetros Configuráveis**
- **`n_dias = 7`**: Janela temporal para análise (últimos 7 dias)
- **`dias_test = 21`**: Número de dias para simulação de trading
- **`quantia = 10000`**: Capital inicial para investimento
- **`n_ativos = 25`**: Número máximo de ativos para análise
- **`epochs = 300`**: Número de épocas para treinamento

### 4. **Arquitetura da Rede Neural**
```python
lin_model = tf.keras.Sequential([
    train_norm,  # Camada de normalização
    tf.keras.layers.Dense(units=1)  # Camada densa de saída
])
```

### 5. **Estratégia de Trading**
- **Análise de tendência**: Compara predições para dias consecutivos
- **Sinal de compra**: Quando `predicao[dia+1] > predicao[dia]`
- **Execução**: Compra até 10 ações por ativo (limitado pelo capital)
- **Gestão de risco**: Controle de posições e capital disponível

### 6. **Sistema de Checkpoints**
- **Salvamento de pesos**: Modelos são salvos após cada treinamento
- **Reutilização**: Pesos são carregados para predições subsequentes
- **Estrutura de pastas**: Organização por janela temporal e ativo

### 7. **Interpretação dos Resultados**
- **Predições**: Valores previstos para cada ativo
- **Portfólio**: Composição da carteira de investimentos
- **Capital**: Evolução do capital ao longo do tempo
- **Performance**: Comparação entre estratégia e buy-and-hold

## 🔍 Estrutura do Código

```
├── Importação de bibliotecas
├── Carregamento de dados financeiros
├── Configuração de parâmetros
├── Pré-processamento e limpeza
├── Loop principal de trading
│   ├── Treinamento de modelos
│   ├── Predição de preços
│   ├── Execução de estratégias
│   └── Atualização de portfólio
├── Sistema de checkpoints
└── Análise de resultados
```

## 📊 Resultados Esperados

Após a execução, você verá:
- Modelos treinados para cada ativo
- Predições de preços futuros
- Composição do portfólio de investimentos
- Evolução do capital ao longo do tempo
- Comparação de performance da estratégia

## 🎯 Aplicações Práticas

Este projeto serve como base para:
- Desenvolver sistemas de trading automatizado
- Implementar estratégias de investimento baseadas em ML
- Analisar padrões em séries temporais financeiras
- Criar modelos de previsão para diferentes ativos
- Estudar aplicações de deep learning em finanças

## ⚠️ Considerações Importantes

- **Arquivo de dados**: Certifique-se de ter o arquivo `Data_trat.csv`
- **Dados financeiros**: Qualidade e limpeza dos dados são cruciais
- **Overfitting**: Modelos podem se ajustar demais aos dados históricos
- **Risco**: Este é um projeto educacional, não uma recomendação de investimento
- **Performance**: Treinamento pode ser computacionalmente intensivo

## 🔒 Aspectos de Segurança

- **Dados sensíveis**: Informações financeiras devem ser tratadas com cuidado
- **Backtesting**: Estratégias devem ser testadas antes de uso real
- **Gestão de risco**: Sempre implemente stop-loss e position sizing
- **Regulamentação**: Considere aspectos legais e regulatórios

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para:
- Reportar bugs
- Sugerir melhorias
- Adicionar novas funcionalidades
- Melhorar a documentação
- Implementar novas estratégias de trading

## 📚 Referências

- [TensorFlow Documentation](https://www.tensorflow.org/)
- [Keras Documentation](https://keras.io/)
- [Pandas Documentation](https://pandas.pydata.org/)
- [Análise de Séries Temporais](https://otexts.com/fpp3/)
- [Machine Learning em Finanças](https://www.quantopian.com/)

---

**Desenvolvido por**: Nicolas Quant  
**Data**: 2024  
**Licença**: MIT  
**⚠️ Aviso**: Este projeto é educacional e não constitui recomendação de investimento
