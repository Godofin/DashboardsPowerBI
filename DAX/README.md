# Funções DAX

## Funções Matemáticas

## SUMX()

- Sumx é utilizado para realizar soma que seriam feitos a partir de colunas calculadas de maneira dinâmica

``` 
    # SumX = SUMX(Tabela, Calculo)
```

## Funções Calculate

### Calculate Filtrando Por Algo

``` 
    #Calculate Filtrando = CALCULATE(
        SOMA(), 
        [CampoTabela] = "Valor campo"
    )

```

### Calculate Usando Filter

``` 
    #Calculate Usando Filter = CALCULATE(
        SOMA(), 
        FILTER(TABELA, [CampoTabela] = "Valor campo")
    )

```
### Calculate Usando In(Podendo utilizar mais valores)

``` 
    #Calculate Usando In = CALCULATE(
        SOMA(), 
        'NomeTabela'[CampoTabela] in {"Valor Campo", "Valor Campo", "Valor Campo"}
    )

```
### Calculate Travando Filtragem da Página

``` 
    #Calculate Usando In = CALCULATE(
        SOMA(), 
        ALL(TabelaCampo)
    )

```

## Funções de Inteligência de Dados Temporais

### DatesBetween

- Faz o cálculo em um determinado intervalo de datas

``` 
    # DatesBetween = CALCULATE(
        [# Total Vendas], 
        DATESBETWEEN('Tb_Calendário'[Date], "01/01/2015", "31/12/2015")
    ) 

```
### Next Year/Month/Quarter

- Faz o cálculo do próximo mês

``` 
    # Next Year = CALCULATE(
        [# Total Vendas], 
        NEXTYEAR/MONTH/QUARTER('Tb_Calendário'[Date])
    )

```

### Previous Year/Month/Quarter

- Faz o cálculo do mês anterior

``` 
    # Previous Year = CALCULATE(
        [# Total Vendas], 
        PREVIOUSYEAR/MONTH/QUARTER('Tb_Calendário'[Date])
    )

```

### Parallel Period

- Faz o cálculo de meses a frente ou atras em um número passado 
- Para meses atrás usar (-numero) e a frente apenas numero


``` 
    # Parallel Period = 
    CALCULATE(
        [# Total Vendas],
        PARALLELPERIOD('Tb_Calendário'[Date], -2, YEAR/MONTH/QUARTER)
    )

```
### DATESYTD

- Faz o calculo cumulativo entre os anos

``` 
    # DATESYTD = CALCULATE(
        [# Total Vendas], 
        DATESYTD('Tb_Calendário'[Date])
    )

```

## Funções de Relação e informativas


### IF(ISBLANK())

```
    # Funcao = VAR TOTAL = SUM(CAMPO1, CAMPO2)

    RETURN IF(ISBLANK(TOTAL), 0, TOTAL)
``` 

