#### **DAX:**

#### LeastSoldPizza:
```
LeastSoldPizza = 
VAR PizzaQuantity =
    SUMMARIZE(
        'order_details',
        'order_details'[pizza_id],
        "TotalQuantity", SUM('order_details'[quantity])
    )
    // I create a summary table with the total quantity of each pizza sold.

VAR MinQuantity = 
    MINX(
        PizzaQuantity,
        [TotalQuantity]
    )
    // I determine the lowest quantity sold among all pizzas.

VAR PizzasWithMinQuantity = 
    FILTER(
        PizzaQuantity,
        [TotalQuantity] = MinQuantity
    )
    // I filter the pizzas that have the lowest sold quantity.

VAR NumberOfPizzasWithMinQuantity = 
    COUNTROWS(PizzasWithMinQuantity)
    // I count how many pizzas have the lowest sold quantity.

VAR LeastSoldPizzaID =
    CALCULATE(
        MAX('order_details'[pizza_id]),
        PizzasWithMinQuantity
    )
    // I get the ID of the pizza with the lowest sold quantity (or one of the least sold in case of a tie).

VAR PizzaTypeID =
    CALCULATE(
        MAX('pizzas'[pizza_type_id]),
        'pizzas'[pizza_id] = LeastSoldPizzaID
    )
    // I find the pizza type ID for the least sold pizza.

VAR PizzaName =
    CALCULATE(
        MAX('pizza_types'[name]),
        'pizza_types'[pizza_type_id] = PizzaTypeID
    )
    // I retrieve the name of the pizza based on its type.

VAR PizzaSize =
    SWITCH(
        CALCULATE(
            MAX('pizzas'[size]),
            'pizzas'[pizza_id] = LeastSoldPizzaID
        ),
        "S", "Small",
        "M", "Medium",
        "L", "Large",
        "XL", "X large",
        "XXL", "XX large",
        MAX('pizzas'[size])
    )
    // I convert the pizza size code into a readable description.

VAR Result = 
    IF(
        ISBLANK(LeastSoldPizzaID),
        "No Sales",
        IF(
            NumberOfPizzasWithMinQuantity > 1,
            "Multiple Tie",
            PizzaName & ", " & PizzaSize
        )
    )
    // I return a message with the name and size of the least sold pizza,
    // or a message indicating a tie or no sales.

RETURN
    Result


```

#### MedianOrder$
```
MedianOrder$ = 
MEDIANX(
    SUMMARIZE(
        orders,
        orders[order_id],
        "Total_Order", [Totalorder$]
    ),
    [Total_Order]
)
```
#### MostSoldPizza
```
MostSoldPizza = 
VAR PizzaQuantity =
    SUMMARIZE(
        'order_details',
        'order_details'[pizza_id],
        "TotalQuantity", SUM('order_details'[quantity])
    )
    // I create a summary table with the total quantity of each pizza sold.

VAR MaxQuantity = 
    MAXX(
        PizzaQuantity,
        [TotalQuantity]
    )
    // I determine the highest quantity sold among all pizzas.

VAR PizzasWithMaxQuantity = 
    FILTER(
        PizzaQuantity,
        [TotalQuantity] = MaxQuantity
    )
    // I filter the pizzas that have the maximum sold quantity.

VAR NumberOfPizzasWithMaxQuantity = 
    COUNTROWS(PizzasWithMaxQuantity)
    // I count how many pizzas have the maximum sold quantity.

VAR MostSoldPizzaID =
    CALCULATE(
        MAX('order_details'[pizza_id]),
        PizzasWithMaxQuantity
    )
    // I get the ID of the most sold pizza (or one of the most sold in case of a tie).

VAR PizzaTypeID =
    CALCULATE(
        MAX('pizzas'[pizza_type_id]),
        'pizzas'[pizza_id] = MostSoldPizzaID
    )
    // I find the pizza type ID for the most sold pizza.

VAR PizzaName =
    CALCULATE(
        MAX('pizza_types'[name]),
        'pizza_types'[pizza_type_id] = PizzaTypeID
    )
    // I retrieve the name of the pizza based on its type.

VAR PizzaSize =
    SWITCH(
        CALCULATE(
            MAX('pizzas'[size]),
            'pizzas'[pizza_id] = MostSoldPizzaID
        ),
        "S", "Small",
        "M", "Medium",
        "L", "Large",
        "XL", "X large",
        "XXL", "XX large",
        MAX('pizzas'[size])
    )
    // I convert the pizza size code into a readable description.

VAR Result = 
    IF(
        ISBLANK(MostSoldPizzaID),
        "No Sales",
        IF(
            NumberOfPizzasWithMaxQuantity > 1,
            "Multiple Tie",
            PizzaName & ", " & PizzaSize
        )
    )
    // I return a message with the name and size of the most sold pizza,
    // or a message indicating a tie or no sales.

RETURN
    Result

```

#### QtyDay_Median
```
QtyDay_Median = 
MEDIANX(
    SUMMARIZE(
        'orders',
        'orders'[Day], 'orders'[Month],
        "TotalQuantity", SUM('order_details'[quantity])
    ),
    [TotalQuantity]
)
```
#### QtyHour_Median
```
QtyHour_Median = 
MEDIANX(
    SUMMARIZE(
        'orders',
        'orders'[HourRange], orders[Month], orders[Day],
        "TotalQuantity", SUM('order_details'[quantity])
    ),
    [TotalQuantity]
)
```
#### Totalorder$
```
Totalorder$ = 
CALCULATE( 
    SUMX(
        order_details,
        order_details[quantity] * RELATED(pizzas[price])
                )
        )
```
#### TotalQty
```
TotalQty = CALCULATE( 
    SUMX(
        order_details,
        order_details[quantity])
                )
```                