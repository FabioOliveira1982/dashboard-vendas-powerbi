# Medidas DAX — Dashboard Comercial

Crie cada expressão em Modelagem > Nova medida, com a tabela `Vendas` selecionada.

```dax
Faturamento =
SUMX(Vendas, Vendas[Quantidade] * Vendas[Preco_Unitario])

Custo Total =
SUMX(Vendas, Vendas[Quantidade] * Vendas[Custo_Unitario])

Lucro Total =
[Faturamento] - [Custo Total]

Margem de Lucro =
DIVIDE([Lucro Total], [Faturamento], 0)

Total de Pedidos =
DISTINCTCOUNT(Vendas[Pedido])

Unidades Vendidas =
SUM(Vendas[Quantidade])

Ticket Medio =
DIVIDE([Faturamento], [Total de Pedidos], 0)

Preco Medio =
DIVIDE([Faturamento], [Unidades Vendidas], 0)

Produtos Vendidos =
DISTINCTCOUNT(Vendas[Produto])
```

## Tabela calendário

Crie uma nova tabela:

```dax
Calendario =
ADDCOLUMNS(
    CALENDAR(MIN(Vendas[Data]), MAX(Vendas[Data])),
    "Ano", YEAR([Date]),
    "MesNumero", MONTH([Date]),
    "Mes", FORMAT([Date], "MMMM"),
    "AnoMes", FORMAT([Date], "YYYY-MM")
)
```

Renomeie `Date` para `Data`, marque a tabela como tabela de datas e relacione `Calendario[Data]` com `Vendas[Data]` em uma relação 1:*.

## Formatação
- Faturamento, Custo Total, Lucro Total e Ticket Medio: moeda (R$).
- Margem de Lucro: porcentagem.
- Pedidos, unidades e produtos: número inteiro.

## Conferência da base
Com as 20 linhas fornecidas: faturamento R$ 81.440,00; custo R$ 58.855,00; lucro R$ 22.585,00; margem 27,73%; 20 pedidos; 147 unidades; ticket médio R$ 4.072,00.

Atenção: dependendo da configuração regional do Power BI, ajuste a localidade de importação para Português (Brasil) para interpretar os decimais com vírgula corretamente.