# 🚗 Previsão de Preço de Carros Usados na Índia

![Carros na Índia](https://conteudo.imguol.com.br/c/noticias/ae/2015/12/16/15out2015---transito-intenso-em-rua-de-nova-deli-india-1450269852888_615x300.jpg)

Este projeto utiliza **Machine Learning** para prever o preço de **carros usados na Índia** com base em diversas características dos veículos. O objetivo é resolver um problema de **regressão supervisionada**, aplicando diferentes algoritmos e técnicas de pré-processamento para melhorar a performance dos modelos.

## 📁 Sobre o Dataset

O conjunto de dados foi obtido do Kaggle e contém informações sobre veículos usados vendidos na Índia. As principais colunas (features) do dataset são:

- `name`: Nome do carro (marca e modelo).
- `year`: Ano de fabricação do veículo.
- `selling_price`: Preço de venda do carro (target).
- `km_driven`: Quilometragem total rodada.
- `fuel`: Tipo de combustível utilizado (Petrol, Diesel, CNG, LPG, Electric).
- `seller_type`: Tipo de vendedor (Dealer, Individual, Trustmark Dealer).
- `transmission`: Tipo de transmissão (Manual ou Automática).
- `owner`: Número de proprietários anteriores.
- `mileage`: Quilometragem por litro (ex: 19.7 kmpl).
- `engine`: Cilindrada do motor (ex: 1248 CC).
- `max_power`: Potência máxima do motor (ex: 74 bhp).
- `seats`: Quantidade de assentos do veículo.
- `torque`: Torque do veículo.

## 🧪 Técnicas Aplicadas

- Remoção de outliers com IQR (Intervalo Interquartil)
- Feature engineering: criação da feature `car_age`
- Encoding de variáveis categóricas com `get_dummies`
- Feature Scaling com `StandardScaler`
- Divisão entre treino e teste com `train_test_split`

## 🤖 Modelos Utilizados

Foram testados diversos modelos de regressão, incluindo:

- Regressão Linear
- Decision Tree Regressor
- Random Forest Regressor
- XGBoost Regressor (melhor desempenho até o momento)

## 🔧 Otimização de Hiperparâmetros

Durante os testes com os modelos, foram utilizados dois algoritmos de busca de hiperparâmetros para melhorar o desempenho dos modelos:

### 📌 GridSearchCV
Realiza uma busca exaustiva em uma grade (*grid*) de combinações possíveis de hiperparâmetros.

Foi utilizado com o **Random Forest Regressor** para encontrar os melhores valores de:

- `n_estimators`
- `max_depth`
- `min_samples_split`
- `min_samples_leaf`

### 🎲 RandomizedSearchCV
Faz uma busca aleatória por combinações de hiperparâmetros dentro de uma distribuição definida, sendo mais rápido e eficiente em grandes espaços de busca.

Utilizado com o **XGBoost Regressor** para encontrar os melhores valores de:

- `n_estimators`
- `max_depth`
- `learning_rate`
- `subsample`
- `colsample_bytree`

Essas técnicas foram implementadas com **validação cruzada (cross-validation)** para garantir que o modelo generalize bem para novos dados.


## 🧮 Métricas de Avaliação

- **RMSE (Root Mean Squared Error)**: usada para medir o erro médio da previsão em relação ao valor real.
- **R² Score**: mede o quão bem os dados se ajustam ao modelo.

## 📌 Conclusão

Apesar de um bom desempenho com XGBoost, os valores de RMSE ainda são relativamente altos, indicando possíveis limitações do dataset (ex: ruído, variáveis ocultas ou ausência de normalização completa do mercado de usados).

## 💻 Como rodar

```bash
# Clone o repositório
git clone https://github.com/LuciosGIT/India-Car-Price-Prediction

# Instale as dependências
pip install -r requirements.txt

# Execute o notebook
jupyter notebook
```

