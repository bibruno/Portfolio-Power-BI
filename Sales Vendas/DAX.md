#### **DAX:**

#### Profit %:
```
Profit% = 
DIVIDE(
    [Total Profit],
    [Total Sales],
    0
)
```
#### Top Category:
```
Top Category = 
MAXX(
    TOPN(
        1,
        SUMMARIZE(
            InputData,
            MasterData[Category],
            "TotalSales", 
            [Total Sales]
        ),
        [Total Sales],
        DESC
    ),
    MasterData[Category]
)
```
#### Top Product:
```
Top Product = 
MAXX(
    TOPN(
        1,
        SUMMARIZE(
            InputData,
            MasterData[Product],
            "TotalSales", 
            [Total Sales]
        ),
        [Total Sales],
        DESC
    ),
    MasterData[Product]
)
```
#### Total Profit:
```
Total Profit = 
SUMX(
    InputData,
    (InputData[Quantity] * (RELATED(MasterData[PRODUCT IDPRODUCT ID]) * (1 - InputData[Discount %]/100))) 
    - (InputData[Quantity] * RELATED(MasterData[BUYING PRIZE]))
)
```
#### Total Sales:

```
Total Sales = 
SUMX(
    InputData, 
    InputData[Quantity] * RELATED(MasterData[PRODUCT IDPRODUCT ID]) * (1 - InputData[Discount %] / 100)
)
```