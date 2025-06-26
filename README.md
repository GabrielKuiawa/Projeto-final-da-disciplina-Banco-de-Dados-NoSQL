# Projeto Final - Banco de Dados NoSQL

Este projeto utiliza **MongoDB** e **Python (pandas, pymongo, seaborn, matplotlib)** para análise de dados de saúde relacionados ao diabetes.

## Como importar o dataset para o MongoDB pelo terminal
mongoimport --db project_bdnsql --collection Healthcare-Diabetes --type csv --headerline --file Healthcare-Diabetes.csv

## Funcionalidades

- **Inserção automática de dados**: Geração e inserção de dados aleatórios na coleção.
- **Edição de documentos**: Atualização de campos específicos em documentos.
- **Busca de documentos**: Consulta de documentos com diferentes operadores e filtros.
- **Exclusão de documentos**: Remoção de documentos da coleção.
- **Funções de agregação**: Cálculo de médias, máximos, mínimos e outras estatísticas agrupadas.
- **Análise exploratória**: Estatísticas descritivas e distribuição de frequência dos dados.
- **Visualização**: Gráficos de boxplot, barras e histogramas para análise visual dos dados.

## Estrutura dos Dados

Cada documento possui os seguintes campos:
- `Id`
- `Pregnancies`
- `Glucose`
- `BloodPressure`
- `SkinThickness`
- `Insulin`
- `BMI`
- `DiabetesPedigreeFunction`
- `Age`
- `Outcome`

## Como executar

1. Certifique-se de ter o MongoDB rodando localmente.
2. Instale as dependências:
   ```bash
   pip install pandas pymongo matplotlib seaborn
   ```
3. Execute o notebook `project bdnsql.ipynb` no VS Code ou Jupyter.

## Exemplos de uso

- **Inserir dados aleatórios**:
  ```python
  data.insert_many([...])
  ```
- **Editar documento**:
  ```python
  data.update_one({"Id": 1}, {"$set": {"Glucose": 150}})
  ```
- **Buscar com operadores**:
  ```python
  data.find({"Glucose": {"$gt": 150}})
  ```
- **Agregação**:
  ```python
  data.aggregate([{"$group": {"_id": "$Outcome", "avg_glucose": {"$avg": "$Glucose"}}}])
  ```
- **Visualização**:
  ```python
  import seaborn as sns
  sns.histplot(df['Glucose'])
  ```

## Visualizações

- Boxplot da glicose por grupo (com/sem diabetes)
- Distribuição por faixa etária e outcome

---

**Autor:** Gabriel  
**Disciplina:** Banco de Dados NoSQL  
**Professor:** Kelly Lais Wiggers