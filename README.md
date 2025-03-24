# Portfólio Power BI 📊

Este portfólio foi criado por **Bruno Bignotto**, um analista de BI com mais de 4 anos de experiência em soluções de análise e visualização de dados. O objetivo deste portfólio é apresentar exemplos de dashboards desenvolvidos em **Power BI** com foco na análise de dados, proporcionando insights relevantes para tomadas de decisão.

Abaixo, você encontrará alguns dos dashboards criados, cada um deles com uma breve descrição sobre os dados, o tratamento aplicado, as principais funcionalidades e possíveis melhorias futuras.

## Dashboards
- [Network](#Network)
- [Aquecimento Global](#aquecimento-global)
- [Pizzaria](#pizzaria)
- [Sales Dashboard](#sales-dashboard)
- [Girassol RH](#girassol-rh)


---
<br>

# Fúnil de Vendas

![Preview do Dashboard](https://i.imgur.com/LhALGBT.gif)
## 📊 Estrutura do Relatório

### 1. Visão Geral (Jan-Mar 2024)
**Insight Central**  
Média de conversão de vendas de apenas 2,64% contra benchmark do setor

**Principais Métricas**  
- 8.968 Leads Gerados
- 406 Leads Qualificados (4,53% do total)
- 236 Vendas Efetivadas

**Visualizações**  
- Cards: Totais de leads e vendas
- Gráfico de Barras: Evolução mensal de leads qualificados vs vendas

**Filtros**  
- Período: 1º Trimestre 2024
- Meses: Jan, Fev, Mar

### 2. Estudo de Caso (Impacto das Campanhas)
**Problema Identificado**  
- Tempo médio de resposta: 76 horas
- Campanhas genéricas geravam 135 leads/mês

**Ação Implementada**  
- Segmentação estratégica a partir de Abril/2024

**Resultado**  
📈 Aumento de 327% nos leads qualificados (média de 443/mês)

**Visualizações**  
- Pizza: Fontes de vendas
- Comparativo antes/depois das campanhas

**Filtros**  
- Período: Jan-Abr 2024

### 3. Resultados Pós-Otimização
**Performance Trimestral**  
- Crescimento de 358,9% nas vendas (Q2 vs Q1)
- Aumento de 301,97% em leads qualificados

**Destaques**  
- Gráfico de conversão trimestral (QoQ)
- Análise por fontes mais eficientes

**Filtros**  
- Período: 1º Semestre 2024

### 4. Perfil do Cliente Ideal
**Características-Chave**  
- Cargos: CTO (32%), Diretor TI (28%), Gerente TI (24%)
- Porte: Empresas >50 funcionários (89%)

**Recomendações**  
- Expandir para:
  - Cargos adjacentes (Gerente Inovação)
  - Empresas 10-50 funcionários

**Visualizações**  
- Funil: Conversão por cargo/porte
- Evolução temporal de métricas

## ⚙️ Como Utilizar
1. Faça download do arquivo `.pbix`
2. Abra no Power BI Desktop (versão 2.120+)
3. Interaja com:
   - Tooltips em gráficos
   - Cross-filtering entre visualizações

## 📁 Fontes de Dados
- Dados gerados em Python
- Pesquisa de Benchmarking (Setor)

## 📌 Insights Chave
1. Campanhas segmentadas aumentaram conversão em 3x
2. Tempo de resposta impacta diretamente na qualificação
3. 72% das vendas vêm de 3 cargos específicos



# Network
Para maiores detalhes, consulte o repositório aqui: <a href="https://github.com/bibruno/Portfolio-Power-BI/tree/main/Network" target="_blank">Repositório -  Network</a>  


![Network](https://i.imgur.com/oeqWcKT.png)

#### Criação dos dados:
Utilizei o Google Sheet para gerar os dados de forma aleatória.
Como a aleatoriedade tende a ser uniforme, variei em alguns trechos o intervalo de aleatoriedade. 

##### Objetivo:
Criar um portfólio que simule ambientes que já lidei.

##### Utilidade:
Através desse dashboard é possível tomar decisões de nível gerencial para melhoria contínua.
Através de 5 páginas, se tem graficamente a representação de dados importantes como; "Quantidade de Chamados por Causa Raiz", "Tempo médio de Resolução" e "Disponibilidade".
<br>

[Voltar para Dashboards](#dashboards)

---
<br>
<br>
<br>
<br>

# Aquecimento Global
<a href="https://github.com/bibruno/Portfolio-Power-BI/tree/main/Clima" target="_blank">Repositório -  Aquecimento Global</a>

![Aquecimento Global](https://i.imgur.com/UprzyHN.jpeg)

#### Tratamento dos dados:

Foram utilizadas originalmente duas tabelas do dataset Global Climate Change Data, sendo elas: GlobalLandTemperaturesByMajorCity e GlobalTemperatures. Destas tabelas, outras se derivaram devido à necessidade de ajustar a granularidade ou resumir as informações.

##### Capitais
Na confecção do gráfico que mostra as oito capitais que tiveram maior aumento de temperatura média anual, optei por resumir os dados em outra tabela, calculando a diferença de temperatura média anual da capital, fazendo o cálculo simples subtraindo o primeiro valor do último valor apresentado. Para facilitar o código e a apresentação do gráfico, os dados foram tratados para a média anual ao invés de vários dados ao longo de cada ano.

##### Global
Para construir o gráfico da previsão de temperatura (parte inferior do relatório), o primeiro passo, logo após carregar os dados, foi ajustar a granularidade, pois as informações eram apresentadas em várias datas ao decorrer de um ano. Foi resumido a média dos dados por ano utilizando DAX para criar uma nova tabela resumindo a fonte original. Com os valores da média agora concentrados por ano, calculei o `vSLOPE` e `vIntercept` fazendo uso do comando `LINESTX`, tornando assim possível o cálculo da Regressão Linear e, consequentemente, as previsões para datas futuras.
<br>

[Voltar para Dashboards](#dashboards)

---
<br>
<br>
<br>
<br>

# Pizzaria
<a href="https://github.com/bibruno/Portfolio-Power-BI/tree/main/Pizzaria" target="_blank">Repositório - Pizzaria</a>


![Gif que exemplifica o funcionamento do Sales Dashboard](https://i.imgur.com/qTdY7KQ.gif)

#### Perguntas respondidas:
1. Quais são os dias e horários mais movimentados?
2. Quantas pizzas estamos fazendo durante os períodos de pico?
3. Quais são nossas pizzas mais e menos vendidas?
4. Qual é o valor médio dos pedidos?

#### Como essas perguntas foram respondidas pelos visuais:
- As perguntas 1 e 2 foram respondidas usando um "Heat Map Visual" (matriz) que exibe a quantidade mediana de pedidos por dia e horário. Além disso, ofereci insights através de Cartões Visuais que mostram os valores totais e medianos de pedidos, assim como as quantidades totais e medianas.
- A pergunta 3 foi respondida usando Cartões Visuais intitulados "Mais Vendida" e "Menos Vendida".
- A pergunta 4 foi respondida usando um Cartão Visual intitulado "Valor Mediano por Pedido."

### Como as fórmulas DAX abordaram as perguntas:

**1. Quais são os dias e horários mais movimentados?**

Para determinar os dias e horários mais movimentados, usei as seguintes fórmulas DAX:
- `QtyDay_Median` calcula a quantidade mediana de pizzas pedidas por dia do mês.
- `QtyHour_Median` calcula a quantidade mediana de pizzas pedidas por hora do dia.

Esses resultados foram visualizados usando um "Heat Map Visual" (matriz) que exibe esses valores medianos. Este mapa de calor me permite identificar padrões e períodos de pico ao longo do dia e da semana, ajudando a entender quando a pizzaria está mais movimentada.

**2. Quantas pizzas estamos fazendo durante os períodos de pico?**

Usei a fórmula `Totalorder$` para calcular a receita total gerada pelas vendas de pizzas, e a fórmula `TotalQty` para determinar a quantidade total de pizzas vendidas. Analisando esses totais durante os períodos de pico, consigo avaliar o volume de produção de pizzas e a geração de receita durante esses horários de alta demanda.

**3. Quais são nossas pizzas mais e menos vendidas?**

Para identificar as pizzas mais e menos vendidas, usei as seguintes fórmulas DAX:
- `MostSoldPizza` determina a pizza com a maior quantidade total vendida, mesmo em caso de empates.
- `LeastSoldPizza` identifica a pizza com a menor quantidade total vendida, também lidando com empates.

Apresentei esses insights usando Cartões Visuais intitulados "Mais Vendida" e "Menos Vendida", que destacam claramente as pizzas de melhor e pior desempenho com base nos dados de vendas.

**4. Qual é o valor médio dos pedidos?**

A fórmula `MedianOrder$` calcula o valor mediano dos pedidos. Visualizando essa métrica através de um Cartão Visual intitulado "Valor Mediano por Pedido," consigo fornecer uma representação clara do valor médio dos pedidos, dando insights sobre o comportamento de compra dos clientes.
<br>
<br>

[Voltar para Dashboards](#dashboards)

---
<br>
<br>
<br>
<br>


# Sales Dashboard
<a href="https://github.com/bibruno/Portfolio-Power-BI/tree/main/Sales%20Vendas" target="_blank">Repositório - Sales Vendas</a>

![Gif que exemplifica o funcionamento do Sales Dashboard](https://i.imgur.com/Khh7jIt.gif)

### Como as fórmulas DAX abordaram as métricas principais:

**1. Percentual de Lucro**

Para calcular o percentual de lucro, usei a fórmula `Profit%`:
- `Profit%` é determinado dividindo o `Lucro Total` pelas `Vendas Totais`. Essa fórmula ajuda a entender a lucratividade das vendas em relação à receita total, fornecendo insights sobre a eficiência do processo de vendas.

**2. Categoria Top**

A fórmula `Top Category` identifica a categoria com as maiores vendas totais:
- `Top Category` usa a função `TOPN` para selecionar a categoria com as maiores vendas totais a partir dos dados resumidos. Isso me permite identificar a categoria que gera mais receita, o que é crucial para a tomada de decisões estratégicas e alocação de recursos.

**3. Produto Top**

De forma semelhante, a fórmula `Top Product` encontra o produto com as maiores vendas totais:
- `Top Product` opera de maneira semelhante à fórmula `Top Category`, mas foca nos produtos individuais. Resumindo os dados de vendas, essa fórmula destaca o produto com melhor desempenho em termos de vendas, oferecendo insights valiosos sobre a popularidade e desempenho dos produtos.

**4. Lucro Total**

Para calcular o lucro total, usei a fórmula `Total Profit`:
- `Total Profit` é calculado somando o lucro de cada transação. A fórmula calcula o lucro considerando a quantidade vendida, o preço de venda após desconto e o preço de compra. Isso fornece uma visão abrangente da lucratividade geral.

**5. Vendas Totais**

A fórmula `Total Sales` calcula a receita total de vendas:
- `Total Sales` é calculada somando o valor das vendas para cada transação. Isso inclui a quantidade vendida, o preço de venda após desconto, e ajuda a entender a receita total gerada com as vendas.
<br>
<br>

[Voltar para Dashboards](#dashboards)

---
<br>
<br>
<br>
<br>

# Girassol RH
<a href="https://github.com/bibruno/Portfolio-Power-BI/tree/main/Girassol%20RH" target="_blank">Repositório - Girassol RH</a>



![Gif que exemplifica o funcionamento do Dashboard RH](https://i.imgur.com/7FLV0gf.gif)

#### Principais elementos da tabela fato:
- cpf_func
- data_nascimento
- genero_func
- status (DAX)
- IDADE_ATUAL (DAX)
- FAIXA_ETARIA (DAX)
- idNivel

#### Principais elementos das tabelas dimensão:
- Nivel (dCargos)
- tipo_func (dTipoFuncionario)
- mês (DAX - dCalendario)
