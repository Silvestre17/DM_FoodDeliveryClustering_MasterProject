# Notas do Notebook

## Umi

> `customer_region`

- MAYBE POR AS MENOS FREQUENTES NUMA CLASSE DE "OUTRAS REG."

> `customer_age`

AGRUPAMENTOS:

- 14 - 17 - CHILDREN
- 18 - 23 - UNI
- 24 - 50 - WORKING MAIS 
- 51 - 64 - WORKING MAS MAIS VELHOS
- 65 - 85 - REFORMED??

VER ESTUDOS QUE POSSAM FZR BACKUP DESTA INFO:
- https://www.supermarketnews.com/grocery-operations/study-why-consumers-select-takeout  isto tem mais a ver do US 
- não podemos analisar se tem alguma coisa a ver com a quarentena porque n temos datas
- https://www.statista.com/outlook/emo/online-food-delivery/worldwide#analyst-opinion



# Filipa

-------------------------------------------------------------------------------------------------- IDEIAS --------------------------------------------------------------------------------------------------

A média e mediana de idades total é igual à média e mediana de idades de clientes que pediram em mais do que 5 chains (iguais ou não); o mesmo acontece com as regiões; gastos médios por tipo de cozinha já é diferente
relacionar is_chain com o gasto total, com a quantidade de produtos pedidos, ou até com a frequência de pedidos

calcular o percentual de pedidos feitos em chains versus não-chains em cada horário. Isso ajudaria a identificar se o comportamento é realmente direcionado às chains ou se é reflexo do volume total de pedidos.

Tentar ver se à medida que o nr de prod aumenta tb aumenta a proporção de pedidos em chain? mas como média de prod. por pedido ???Qual a proporção média do nr de pedidos em chains/nr de pedidos---> como arranjo nr pedidos podem ter sido mandadas vir da mesma chain ou não certos sítios ou idades ser freq Proporção entre chain e restaurantes independentes.Gráfico de barras ou gráfico de pizza Estará correlacionado com: Gasto total: Os clientes que preferem chains gastam mais ou menos em média? Tipos de culinária: Existe uma diferença nos tipos de culinária preferidos entre quem pede de chains e independentes? Frequência de pedidos: Clientes que preferem chains fazem pedidos com mais ou menos frequência?


---

> `is_chain`

Esta variável toma valores entre 0 e 83 e não tem missings (31888 obs) 
    
    [NÃO É BEM VDD!! 🔴]

Durante os 3 meses foi mais frequente os consumidores mandarem vir de 1,0,2,3...chains pois:

Mais de 50% (precisamente 64,43%) dos consumidores mandaram vir entre [0,2] pedidos de chains

Mais de 75% (precisamente 76,02%) dos consumidores mandaram vir entre [0,3] pedidos de chains   
Os pedidos em chains costuma ser mais de forma pontual


(+ estatística)   
Assimetria: 4.99 dist. assimétrica à direita(+). A maioria dos clientes faz poucos pedidos em chains e um pequeno número de clientes faz muitos pedidos.   
Média: 2.818866031108881 que está de acordo com a assimetria   
Mediana: 2.0

> DECIDIR SE VAMOS USAR A VARIÁVEL `is_chain` COMO CATEGÓRICA OU NUMÉRICA


### Correlações

Independentemente da intensidade, a correlação da variável is_chain com as demais é positiva com exceção da variável first_order: quanto mais tarde foi feito o 1º pedido menos quantidades de pedidos vindos de chains foram feitos ao longo dos 3 meses. É natural porque fizeram poucos pedidos quer chain quer não

corr com product_count e vendor_count não diz muito Um valor alto de product_count indica que o cliente fez muitos "pedidos", o que geralmente implica um maior número de pedidos em chains, mas também pode implicar um maior número de pedidos em restaurantes independentes. A mesma lógica aplica-se a vendor_count: mais fornecedores indicam maior variedade de pedidos, mas isso não necessariamente significa que todos são de chains. É importante considerar que um cliente pode ser mais propenso a experimentar diferentes restaurantes, independentemente de serem chains ou independentes.

DOW (Day of the Week) As altas correlações com DOW também não dizem nada

As var HR_... indicam um maior pedidos de restaurantes chains às 11, 12, 18, 19, 13 e 17, não quer dizer que a percentagem de pedidos em restaurantes chain aumente sequer, é importante considerar que podem ser momentos de alta procura de pedidos em geral, o que inclui tanto chains quanto restaurantes independentes. As horas mais comuns são 17, 11, 16, 18, 10, 12

CUI_Chicken Dishes e noodles talvez seja o tipo de restaurante onde é mais comum mandar vir chain CUI_Asian,CUI_American CUI_Street Food / Snacks,CUI_Italian,CUI_OTHER,CUI_Japanese, CUI_Beverages, CUI_Indian


##### age [Relevante? 🟡]

Dos 12778 consumidores que caem no filtro (percent_chain = 1), mais de 6000 (47.4%) tem idades entre os 21 e os 27
Idade média: 27.45
Idade mínima: 15.0
Idade máxima: 77.0

Dos 21990 consumidores que caem no filtro (percent_chain >= 0.5), mais de 13661 (62.1%) tem idades entre os 20 e os 29
Idade média: 27.49
Idade mínima: 15.0
Idade máxima: 80.0
Mas isto já ocorre df_filtered (31750 obs) (aprox. 48% entre os 21 aos 27 e 62% entre os 20 aos 29)




---

> `order_hour`
