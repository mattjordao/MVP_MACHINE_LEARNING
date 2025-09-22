**Projeto Desenvolvido por**: Mattheus Jordão Monteiro  
**Matrícula**: 4052025000505  
**Contato**: mattjordao@hotmail.com  
**Data**: 28/09/2025


# Classificação de Parkinson através de Análise de Voz

## 📋 Descrição do Projeto
Este projeto implementa um sistema de classificação para detecção da doença de Parkinson utilizando medidas de voz. O modelo de machine learning é capaz de distinguir entre indivíduos saudáveis e com Parkinson com alta acurácia, demonstrando o potencial de técnicas de análise de voz como ferramenta auxiliar no diagnóstico precoce.

## 🎯 Objetivo
Desenvolver e comparar diferentes algoritmos de classificação para prever a presença da doença de Parkinson com base em 22 atributos biomédicos de voz, alcançando 92.3% de acurácia e AUC de 0.98 no melhor modelo.

## 📊 Dataset
**Fonte**: UCI Machine Learning Repository

**Características Gerais**:
- **Registros**: 195 exames de voz
- **Atributos**: 22 medidas biomédicas + variável alvo
- **Classes**:
  - **0**: Saudável (48 registros)
  - **1**: Parkinson (147 registros)

**Característica Principal**: Dados tabulares com medidas de voz como jitter, shimmer, HNR, etc.

## 🏗️ Arquitetura do Projeto
### Estrutura de Diretórios:
- **📊 parkinson_classification.ipynb**: Notebook principal com toda a implementação
- **📋 README.md**: Documentação completa do projeto
- **📈 results/**: Pasta contendo visualizações e resultados
  - `confusion_matrix.png`: Matriz de confusão dos modelos
  - `roc_curves.png`: Curvas ROC de comparação
  - `feature_importance.png`: Importância das features
- **📁 data/**: Diretório para armazenamento de dados (carregado via URL)

## ⚙️ Metodologia

### 1. Pré-processamento
- **Seleção de Features**: Top 10 atributos mais correlacionados
- **Normalização**: StandardScaler para todas as features
- **Divisão dos dados**: 80% treino, 20% teste (estratificado)

### 2. Modelos Implementados
- **🔵 Regressão Logística** (Baseline)
- **🌲 Random Forest** com otimização de hiperparâmetros
- **🎯 SVM** com kernel RBF
- **⚡ Gradient Boosting** (XGBoost-like)

### 3. Avaliação
- **Validação Cruzada**: 5-fold cross-validation
- **Métricas**: Acurácia, AUC-ROC, Precision, Recall, F1-Score
- **Otimização**: Grid Search para hiperparâmetros

## 📈 Resultados

### Desempenho dos Modelos (Test Set)
| Modelo | Acurácia | AUC-ROC | Precision | Recall | F1-Score |
|--------|----------|---------|-----------|--------|----------|
| Gradient Boosting | 92.3% | 0.98 | 0.94 | 0.94 | 0.94 |
| Random Forest | 89.7% | 0.96 | 0.91 | 0.94 | 0.92 |
| SVM | 87.2% | 0.95 | 0.89 | 0.94 | 0.91 |
| Logistic Regression | 84.6% | 0.93 | 0.86 | 0.94 | 0.90 |

### Features Mais Importantes
- **MDVP:Fo(Hz)** - Frequência vocal média
- **spread2** - Medida de espalhamento espectral
- **PPE** - Medida de entropia de perturbação periódica
## 💡 Principais Insights

### ✅ Pontos Fortes
- **Alta acurácia (92.3%)** no conjunto de teste
- **Balanço entre precision e recall** (0.94 ambos)
- **Excelente AUC-ROC (0.98)** indicando grande poder discriminativo
- **Feature selection eficaz** com as 10 variáveis mais relevantes

### ⚠️ Limitações
- **Dataset pequeno** (195 amostras)
- **Desbalanceamento de classes** (75% Parkinson vs 25% Saudável)
- **Necessidade de validação externa**

## 🎯 Aplicações Práticas
- **Triagem inicial** para suspeita de Parkinson
- **Ferramenta auxiliar** para profissionais de saúde
- **Monitoramento longitudinal** de pacientes

## 🔮 Próximos Passos
- **Coleta de mais dados** para melhor generalização
- **Implementação de técnicas para desbalanceamento** (SMOTE)
- **Desenvolvimento de interface web** para uso clínico
- **Validação com dataset independente** externo

## 👥 Contribuição
Contribuições são bem-vindas! Sinta-se à vontade para:
- **Reportar issues**
- **Sugerir melhorias**
- **Adicionar novos modelos**
- **Expandir a análise**

## 📄 Licença
Este projeto está sob a licença MIT. Veja o arquivo LICENSE para detalhes.

## 📚 Referências
- Little, M. A., McSharry, P. E., Roberts, S. J., Costello, D. A., & Moroz, I. M. (2007). Exploiting nonlinear recurrence and fractal scaling properties for voice disorder detection. BioMedical Engineering OnLine, 6(1), 23.
- UCI Machine Learning Repository: Parkinson Dataset
