# DIO - Desafio de Modelagem e Transformação de Dados com DAX

## Objetivo
O desafio consiste em criar um diagrama dimensional utilizando o modelo de esquema em estrela (star schema) com base na tabela **Financial Sample**, assim como a utilização de DAX (*Data Analysis Expressions*) para a criação de colunas e de uma tabela.


## Modelagem
A tabela fato (*fact table*) e as tabelas dimensão (*dimension table*), identificadas respectivamente pelas letras F e D no início de seus nomes, foram criadas duplicando a tabela *financials* original e seguindo as seguintes regras:

- **D_Produtos**: 
  - ID_produto
  - Produto
  - Média de Unidades Vendidas
  - Médias do valor de vendas
  - Mediana do valor de vendas
  - Valor máximo de Venda
  - Valor mínimo de Venda

- **D_Produtos_Detalhes**: 
  - ID_produtos
  - Discount Band
  - Sale Price
  - Units Sold
  - Manufactoring Price

- **D_Descontos**: 
  - ID_produto
  - Discount
  - Discount Band

- **D_Detalhes**: 
  - Informações não contempladas nas demais tabelas dimensão para detalhes adicionais sobre vendas

- **F_Vendas**: 
  - SK_ID
  - ID_Produto
  - Produto
  - Units Sold
  - Sales Price
  - Discount Band
  - Segment
  - Country
  - Salers
  - Profit
  - Date

Para a criação das colunas da tabela **D_Produtos**, durante a transformação dos dados com o Power Query utilizou-se a opção `Agrupar por`, onde então foi selecionada a coluna *Product* e, nas opções avançadas, foram selecionadas as operações *Média*, *Mediana*, *Máximo* e *Mínimo*.

A tabela dimensão **D_Calendário** foi criada usando DAX através da seguinte expressão:

 `D_Calendar = CALENDAR(MIN(F_Sales[Date]),MAX(F_Sales[Date]))`



# DIO---Desafio-Modelagem-e-Transforma-o-de-Dados-com-DAX
Repositório criado para armazenar o resultado de um desafio de projeto envolvendo modelagem dimensional e utilização de DAX (Data Analysis Expressions).
