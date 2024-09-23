

# Scout de Jogadores do Brasileirão 2023
> Machine Learning | Regression Models | RPA

## 💡 Objetivo

O objetivo desse projeto é definir um modelo capaz de mapear o mercado de atletas de futebol que atuaram no campeonato brasileiro de 2023. A ideia central desenvolvida foi construir um modelo que entendesse quais estatísticas de desempenho mais impactam na definição de valor de mercado de cada atleta, e predizer esse valor através delas. 

A intenção não é exatamente gerar um modelo que diga precisamente qual valor deve ser pago em cada atleta, por mais que haja uma resposta próxima a essa, não há o interesse de avaliar critérios como tempo de contrato, capacidade financeira do clube, entre outros fatores determinantes nessa análise. O objetivo principal é fazer uma relação entre o rendimento em estatísticas de jogo e o valor do atleta, buscando encontrar atletas que têm produzido mais do que são avaliados pelo mercado.

O mapeamento do mercado se dá através da análise do erro em relação ao valor predito pelo modelo de regressão associado às estatísticas de desempenho e o valor dado ao atleta pelo mercado. Dessa maneira, é possível separar o mercado entre oportunidades de jogadores subvalorizados e negociações de risco com jogadores supervalorizados.

## 🧠 Estrutura da Modelagem
#### 🤖 Coleta de dados

Os dados das estatísticas dos jogadores foram extraídos do *Sofascore* através de técnicas de RPA. Para instrumentalizar esse processo de coleta de dados foi utilizado o pacote **Selenium** para que automação fosse feita.

#### 📋 Feature Selection

Um grande número de estatísticas de desempenho estão disponíveis no *Sofascore*, o que cria um desafio para aplicação do modelo de regressão. Para evitar o *overfitting* do modelo é necessário selecionar as estatísticas mais correlacionados com o valor de mercado do atleta, e para isso foi utilizado o modelo **SelectKBest** do *Scikit-Learn*.

#### 📈 Regressão
Para a definição do tipo de regressão foram feitos testes com diferentes modelos, utilizando o método de *cross validation*. Avaliando a acurácia de acordo com o erro quadrático médio e a consistência dos modelos foi feita a opção pelo **Support Vector Machine (SVM)**.

