# Portfólio Power BI 📊

Estes são alguns exemplos de dashboards simples e funcionais.

- [Pizzaria](https://github.com/bibruno/Portfolio-Power-BI/tree/master/Pizzaria)
- [Sales Vendas](https://github.com/bibruno/Portfolio-Power-BI/tree/master/Sales%20Vendas)
- [Dashboard RH](https://github.com/bibruno/Portfolio-Power-BI/tree/master/Girassol%20RH)

## Pizzaria [ENG]

![Gif que exemplifica o funcionamento do Sales Dashboard](https://i.imgur.com/qTdY7KQ.gif)

#### Questions to be answered:
1. What days and times do we tend to be busiest?
2. How many pizzas are we making during peak periods?
3. What are our best and worst selling pizzas?
4. What's our average order value?


#### How they were answered by the Visuals:
  - Questions 1 and 2 were answered using a "Heat Map Visual" (matrix) that displays the median order quantity for each day and hour. Additionally, I provided insights through Visual Cards that show the total and median values for orders, as well as the total and median quantities.
  - Question 3 was answered using Visual Cards titled "Best Seller" and "Worst Seller."
  - Question 4 was answered using Visual Cards titled "Median Value per Order."
### How the DAX Formulas Addressed the Questions

**1. What days and times do we tend to be busiest?**

To determine the busiest days and times, I used the following DAX formulas:
- `QtyDay_Median` calculates the median quantity of pizzas ordered for each day of the month.
- `QtyHour_Median` calculates the median quantity of pizzas ordered for each hour of the day.

I visualized these results using a "Heat Map Visual" (matrix) that displays these median values. This heat map allows me to identify patterns and peak periods throughout the day and week, helping me understand when the restaurant is busiest.

**2. How many pizzas are we making during peak periods?**

I used the `Totalorder$` formula to calculate the total revenue generated from pizza sales, and the `TotalQty` formula to determine the total quantity of pizzas sold. By analyzing these totals during peak periods, I can gauge the volume of pizza production and revenue generation during these high-demand times.

**3. What are our best and worst selling pizzas?**

To identify the best and worst selling pizzas, I employed the following DAX formulas:
- `MostSoldPizza` determines the pizza with the highest total quantity sold, even in case of ties.
- `LeastSoldPizza` identifies the pizza with the lowest total quantity sold, handling ties similarly.

I presented these insights using Visual Cards titled "Best Seller" and "Worst Seller," which clearly highlight the top-performing and underperforming pizzas based on sales data.

**4. What's our average order value?**

The `MedianOrder$` formula calculates the median value of orders. By visualizing this metric through a Visual Card titled "Median Value per Order," I can provide a clear representation of the average order value, giving insights into customer spending behavior.

## Sales Dashboard [ENG]

![Gif que exemplifica o funcionamento do Sales Dashboard](https://i.imgur.com/Khh7jIt.gif)

### How the DAX Formulas Addressed the Key Metrics

**1. Profit Percentage**

To calculate the profit percentage, I used the `Profit%` formula:
- `Profit%` is determined by dividing `Total Profit` by `Total Sales`. This formula helps in understanding the profitability of the sales relative to the total revenue, providing insight into the efficiency of the sales process.

**2. Top Category**

The `Top Category` formula identifies the category with the highest total sales:
- `Top Category` uses the `TOPN` function to select the category with the maximum total sales from the summarized data. This allows me to pinpoint the category that generates the most revenue, which is crucial for strategic decision-making and resource allocation.

**3. Top Product**

Similarly, the `Top Product` formula finds the product with the highest total sales:
- `Top Product` operates in a manner similar to the `Top Category` formula but focuses on individual products. By summarizing sales data, this formula highlights the product that performs best in terms of sales, offering valuable insights into product popularity and performance.

**4. Total Profit**

To calculate the total profit, I used the `Total Profit` formula:
- `Total Profit` is computed by summing up the profit for each transaction. The formula calculates profit by considering the quantity sold, the selling price after discount, and the buying price. This provides a comprehensive view of overall profitability.

**5. Total Sales**

The `Total Sales` formula calculates the total sales revenue:
- `Total Sales` is computed by summing up the sales value for each transaction. This includes the quantity sold, the selling price after discount, and helps in understanding the total revenue generated from sales.

By utilizing these DAX formulas, I was able to effectively analyze and present key sales metrics, including profit margins, top-performing categories and products, and overall sales and profit figures.


## Girassol RH [PT-BR]

![Gif que exemplifica o funcionamento do Dashboard RH](https://i.imgur.com/7FLV0gf.gif)

#### Principais elementos da tabela fato:
- cpf_func
- data_nascimento
- genreo_func
- status (DAX)
- IDADE_ATUAL (DAX)
- FAIXA_ETARIA (DAX)
- idNivel

#### Principais elementos das tabelas dimensão:
- Nivel (dCargos)
- tipo_func (dTipoFuncionario)
- mês (DAX - dCalendario)