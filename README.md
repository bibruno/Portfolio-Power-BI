# Portfólio Power BI 📊

Estes são alguns exemplos de dashboards simples e funcionais.

- [Dashboard RH](https://github.com/bibruno/Portfolio-Power-BI/tree/master/Girassol%20RH)

### Dashboard Financeiro

![Gif que exemplifica o funcionando do Dashboard Financeiro](https://i.imgur.com/7FLV0gf.gif[/img])


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
- mes (DAX - dCalendario)



#### **DAX:**
- Status do colaborador: **STATUS = IF(tbFato[data_demissao] = BLANK(),"ATIVO","DESLIGADO")**
- Idade Atual: **IDADE_ATUAL = 
DATEDIFF (\
    tbFato[data_nascimento].[Date],\
    TODAY(),\
    YEAR\
)**
- Faixa etária: **FAIXA ETARIA = 
SWITCH(\
    TRUE(),\
    tbFato[IDADE_ATUAL] <= 18,"0-18",\
    tbFato[IDADE_ATUAL]> 18 && tbFato[IDADE_ATUAL] <=25,"19-25",\
    tbFato[IDADE_ATUAL]> 25 && tbFato[IDADE_ATUAL] <=35,"26-35",\
    tbFato[IDADE_ATUAL]> 35 && tbFato[IDADE_ATUAL] <=45,"36-45",\
    tbFato[IDADE_ATUAL]> 45 && tbFato[IDADE_ATUAL] <=55,"46-55",\
    ">55"\
)**
- Funcionários ativos: **ATIVOS = COUNTROWS(FILTER(tbFato, tbFato[STATUS] = "ATIVO"))**
- Contratações: **CONTRATAÇÕES = DISTINCTCOUNT(tbFato[cpf_func])**
- Demissões: **DEMISSÕES = COUNTROWS(FILTER(tbFato, tbFato[STATUS] = "DESLIGADO"))**
- Contagem de Homens:
**CONTMASC = COUNTROWS(FILTER(tbFato, tbFato[genero_func] = "MASCULINO"))**

- Contagem de Mulheres:
**CONTFEM = COUNTROWS(FILTER(tbFato, tbFato[genero_func] = "FEMININO"))**

- Demisões: **DEMISSÕES = COUNTROWS(FILTER(tbFato, tbFato[STATUS] = "DESLIGADO"))**
\
\
\
\
\
\
\
**Quantidade de dados: 11.323** 



