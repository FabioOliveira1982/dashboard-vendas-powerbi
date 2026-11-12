# Dashboard Comercial — Análise de Vendas

## Sobre
Projeto de Business Intelligence desenvolvido com Power BI Desktop para analisar uma base comercial demonstrativa e transformar dados em indicadores de desempenho.

## Indicadores
- Faturamento, custo e lucro.
- Margem de lucro.
- Total de pedidos e unidades vendidas.
- Ticket médio.
- Produtos vendidos.

## Análises sugeridas
- Evolução mensal do faturamento (gráfico de linhas).
- Faturamento por região (barras).
- Lucro por categoria (barras).
- Vendas por produto (rosca).
- Cartões para faturamento, lucro, margem, pedidos e ticket médio.
- Segmentadores de período, região, categoria e vendedor.

## Tecnologias
Power BI Desktop, DAX, CSV e modelagem de dados.

## Estrutura
- `dados/vendas.csv`: base sintética de vendas.
- `medidas/medidas-dax.md`: medidas e tabela calendário.
- `dashboard-vendas.pbix`: arquivo do relatório, a ser salvo no Power BI Desktop após a montagem.

## Como montar
1. Abra o Power BI Desktop.
2. Use Obter Dados > Texto/CSV e selecione `dados/vendas.csv`.
3. Configure o delimitador como ponto e vírgula e a localidade Português (Brasil), se necessário.
4. Confira os tipos: Data como data; Quantidade como inteiro; preços e custos como decimal/moeda.
5. Renomeie a consulta para `Vendas` e aplique.
6. Crie as medidas documentadas em `medidas/medidas-dax.md`.
7. Crie a tabela Calendario, marque-a como tabela de datas e estabeleça o relacionamento com Vendas.
8. Monte os visuais e salve como `dashboard-vendas.pbix` na raiz deste repositório.

## Resultados de referência
Faturamento R$ 81.440,00; custo R$ 58.855,00; lucro R$ 22.585,00; margem 27,73%; 20 pedidos; 147 unidades; ticket médio R$ 4.072,00.

## Dados e limitações
Todos os dados são fictícios e destinados a estudo/portfólio. O arquivo PBIX não é incluído automaticamente: precisa ser gerado no Power BI Desktop seguindo as instruções acima.

## Autor
Fábio Oliveira  
GitHub: https://github.com/FabioOliveira1982  
LinkedIn: https://www.linkedin.com/in/fabio-oliveira-br/