# Tech Challenge IADT - Fase 1  
## Sistema de Apoio ao Diagnóstico de ECG com Machine Learning  

Este projeto tem como objetivo o desenvolvimento de um modelo de **classificação binária de exames de ECG**, capaz de identificar automaticamente se um exame é **“Saudável” (0)** ou **“Doente” (1)**, com base em medidas extraídas do dataset público **PTB-XL**.  

O modelo final, baseado em **Random Forest**, prioriza a sensibilidade (*recall*) para garantir que potenciais casos patológicos não sejam ignorados. Trata-se de um sistema de apoio à decisão médica, voltado à **triagem automática de exames**, contribuindo para otimizar a rotina de análise clínica.  

---

## Execução no Google Colab

### 1. Acesse o Google Colab e o notebook do projeto  
Abra o ambiente do Google Colab em [https://colab.research.google.com/](https://colab.research.google.com/) com sua conta Google, **ou acesse diretamente o notebook do projeto pelo link abaixo:**  
[**TechChallenge_EGC.ipynb**](https://colab.research.google.com/drive/1mJqV5eKDc3xjah4BMEylOObCedZRIaDI?usp=sharing)

### 2. Faça o upload dos datasets  
Baixe os arquivos públicos disponíveis no repositório oficial do **PhysioNet**:

- [12sl_features.csv](https://physionet.org/content/ptb-xl-plus/1.0.1/features/12sl_features.csv)  
- [ptbxl_database.csv](https://physionet.org/content/ptb-xl/1.0.3/ptbxl_database.csv)  
- [scp_statements.csv](https://physionet.org/content/ptb-xl/1.0.3/scp_statements.csv)  

No Colab, acesse o menu lateral esquerdo (ícone de pasta) e envie os três arquivos para o diretório raiz (`/content/`).

### 3. Ajuste o caminho base (se necessário)
Confirme se o caminho definido no início do notebook está correto:
```python
path = '/content/'
```

### 4. Instale as dependências
Execute o comando abaixo na primeira célula:
```python
!pip install pandas numpy matplotlib seaborn scikit-learn
```

### 5. Execute as células em sequência  
O notebook está dividido em seções numeradas, cobrindo desde o pré-processamento até o treinamento, avaliação e interpretação dos modelos.

---

## Saídas Principais

Durante a execução, o notebook gera:

- Gráficos de análise exploratória (valores nulos, distribuição de classes, correlação entre variáveis);  
- Métricas de desempenho dos modelos (*accuracy*, *recall*, *f1-score*, *ROC-AUC*);  
- Matrizes de confusão;  
- Gráfico de importância das *features* para o modelo final (Random Forest).  

---

## Resultados

| Modelo | Acurácia | Recall (Doente) | ROC-AUC |
|--------|-----------|-----------------|----------|
| Decision Tree (baseline) | 0.8219 | 0.8478 | 0.8172 |
| Random Forest (final) | 0.8824 | 0.9034 | 0.9504 |

O modelo **Random Forest** apresentou desempenho superior ao baseline em todos os indicadores, com destaque para o **recall de 90%** e **ROC-AUC de 0.95**, demonstrando excelente capacidade de distinguir exames saudáveis de doentes.  

---

## Conclusão

O projeto demonstrou a viabilidade de se construir um **modelo de Machine Learning para triagem automática de exames de ECG**.  
O modelo Random Forest obteve **alta acurácia e sensibilidade**, sendo capaz de identificar a maioria dos pacientes com potenciais anormalidades cardíacas.  

A análise de importância das *features* revelou alinhamento com variáveis clinicamente relevantes, reforçando a interpretabilidade do modelo.  

Como sistema de apoio à decisão, a solução pode ser integrada ao fluxo de trabalho hospitalar, priorizando exames com maior probabilidade de alterações e otimizando o tempo da equipe médica.  

---

## Referências

1. Wagner, P. et al. (2020). *PTB-XL, a large publicly available electrocardiography dataset.* *Scientific Data*, 7(154). DOI: [10.1038/s41597-020-0495-6](https://doi.org/10.1038/s41597-020-0495-6)  
2. PhysioNet. *PTB-XL: A large publicly available electrocardiography dataset.* Disponível em: [https://physionet.org/content/ptb-xl/1.0.3/](https://physionet.org/content/ptb-xl/1.0.3/)  
3. Géron, A. (2022). *Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow (3rd ed.)*. O’Reilly Media.  
4. James, G., Witten, D., Hastie, T., & Tibshirani, R. (2021). *An Introduction to Statistical Learning (2nd ed.)*. Springer.  

---

## Autores

- Joalisson dos Santos Borges  
- Luis Gustavo Santini  
- Marina Souza Lucas  
- Ivna Cavalcante Barros Meireles  
- Diego Santos Via  
