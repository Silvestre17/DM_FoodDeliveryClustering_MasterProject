# Notas do Notebook

## Umi

> `customer_region`

- MAYBE POR AS MENOS FREQUENTES NUMA CLASSE DE "OUTRAS REG."

<BR><BR>

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

<BR><BR>

# Filipa

-------------------------------------------------------------------------------------------------- IDEIAS --------------------------------------------------------------------------------------------------

A média e mediana de idades total é igual à média e mediana de idades de clientes que pediram em mais do que 5 chains (iguais ou não); o mesmo acontece com as regiões; gastos médios por tipo de cozinha já é diferente
relacionar is_chain com o gasto total, com a quantidade de produtos pedidos, ou até com a frequência de pedidos

calcular o percentual de pedidos feitos em chains versus não-chains em cada horário. Isso ajudaria a identificar se o comportamento é realmente direcionado às chains ou se é reflexo do volume total de pedidos.

Tentar ver se à medida que o nr de prod aumenta tb aumenta a proporção de pedidos em chain? mas como média de prod. por pedido ???Qual a proporção média do nr de pedidos em chains/nr de pedidos---> como arranjo nr pedidos podem ter sido mandadas vir da mesma chain ou não certos sítios ou idades ser freq Proporção entre chain e restaurantes independentes.Gráfico de barras ou gráfico de pizza Estará correlacionado com: Gasto total: Os clientes que preferem chains gastam mais ou menos em média? Tipos de culinária: Existe uma diferença nos tipos de culinária preferidos entre quem pede de chains e independentes? Frequência de pedidos: Clientes que preferem chains fazem pedidos com mais ou menos frequência?

<BR><BR>
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


<BR><BR>

### Correlações

Independentemente da intensidade, a correlação da variável is_chain com as demais é positiva com exceção da variável first_order: quanto mais tarde foi feito o 1º pedido menos quantidades de pedidos vindos de chains foram feitos ao longo dos 3 meses. É natural porque fizeram poucos pedidos quer chain quer não

corr com product_count e vendor_count não diz muito Um valor alto de product_count indica que o cliente fez muitos "pedidos", o que geralmente implica um maior número de pedidos em chains, mas também pode implicar um maior número de pedidos em restaurantes independentes. A mesma lógica aplica-se a vendor_count: mais fornecedores indicam maior variedade de pedidos, mas isso não necessariamente significa que todos são de chains. É importante considerar que um cliente pode ser mais propenso a experimentar diferentes restaurantes, independentemente de serem chains ou independentes.

DOW (Day of the Week) As altas correlações com DOW também não dizem nada

As var HR_... indicam um maior pedidos de restaurantes chains às 11, 12, 18, 19, 13 e 17, não quer dizer que a percentagem de pedidos em restaurantes chain aumente sequer, é importante considerar que podem ser momentos de alta procura de pedidos em geral, o que inclui tanto chains quanto restaurantes independentes. As horas mais comuns são 17, 11, 16, 18, 10, 12

CUI_Chicken Dishes e noodles talvez seja o tipo de restaurante onde é mais comum mandar vir chain CUI_Asian,CUI_American CUI_Street Food / Snacks,CUI_Italian,CUI_OTHER,CUI_Japanese, CUI_Beverages, CUI_Indian

<BR><BR>

##### `age` [Relevante? 🟡]

Dos 12778 consumidores que caem no filtro (percent_chain = 1), mais de 6000 (47.4%) tem idades entre os 21 e os 27
Idade média: 27.45
Idade mínima: 15.0
Idade máxima: 77.0

Dos 21990 consumidores que caem no filtro (percent_chain >= 0.5), mais de 13661 (62.1%) tem idades entre os 20 e os 29
Idade média: 27.49
Idade mínima: 15.0
Idade máxima: 80.0
Mas isto já ocorre df_filtered (31750 obs) (aprox. 48% entre os 21 aos 27 e 62% entre os 20 aos 29)


#### `customer_region` [Relevante? 🟡]

Dos 12778 consumidores que caem no filtro (percent_chain = 1), mais de 11119 (87%) são das regiões: 2360, 4660, 8670    
46.2% só da região 2360

Dos 21990 consumidores que caem no filtro (percent_chain >= 0.5), mais de 19405 (88.2%) são das regiões: 2360, 4660, 8670   
37.4% só da região 2360   
Mas isto já ocorre df_filtered (31750 obs)

| Segmento                                |        8670      |      4660      |     2360     |
|-----------------------------------------|------------------|----------------|--------------|
| Consumidores c/ `order_count` > 0        | 30.3             | 30.1           | 27.8         |
| "  " & `percent_chain` == 1              | 21.2             | 19.7           | 46.2         |
|"  " &  `percent_chain` >= 0.5            | 26.3             | 24.5           | 37.4         |

<BR><BR>


##### `vendor_count`

df_filtered (31750 obs)   
Vendor count médio: 3.12   
Vendor count mínimo: 1   
Vendor count máximo: 41   

Dos 12778 consumidores que caem no filtro (percent_chain = 1), 84.3%  têm vendor_count entre 1 a 3   
Vendor count médio: 2.29   
Vendor count mínimo: 1   
Vendor count máximo: 30   

Dos 21990 consumidores que caem no filtro (percent_chain >= 0.5), 86% têm vendor_count entre 1 a 5           
Vendor count médio: 3.27   
Vendor count mínimo: 1   
Vendor count máximo: 41 



| Segmento                                |        1      |      2      |     3     |
|-----------------------------------------|------------------|----------------|--------------|
| Consumidores c/ `order_count` > 0        | 28.5             | 26.9           | 16.3         |
| "  " & `percent_chain` == 1              | 41.1             | 28.9           | 14.3         |
|"  " &  `percent_chain` >= 0.5            | 23.9             | 29.5           | 16.3         |

<BR><BR>

##### `product_count`

1__ 14.8%
2__ 19.8%
3__ 15.7%
df_filtered (31750 obs)
Product count médio: 5.69
Product count mínimo: 0
Product count máximo: 269

Dos 12778 consumidores que caem no filtro (percent_chain = 1), 75.3% têm product_count entre 1 a 4
Product count médio: 3.82
Product count mínimo: 1
Product count máximo: 88

Dos 21990 consumidores que caem no filtro (percent_chain >= 0.5), 74% têm product_count entre 1 a 6
Product count médio: 5.78
Product count mínimo: 1
Product count máximo: 269

<BR><BR>


##### `order_hour - HR_...`

A hora mais comum para os consumidores com filtro order_count' > 0 fazerem pedidos é: HR_17 com um total de 12467 pedidos
A hora mais comum para os consumidores com filtro order_count' > 0 e percent_chain = 1 fazerem pedidos é: HR_11 com um total de 3778 pedidos
A hora mais comum para os consumidores com filtro order_count' > 0 e percent_chain >= 0.5 fazerem pedidos é: HR_11 com um total de 9191 pedidos

De notar que somam as os pedidos das horas todas e dão a resposta, ou seja, não vão pessoa a pessoa ver a que hora ela fez mais pedidos (é outra possível análise)

<BR><BR>

##### `DOW..`

O dia mais comum para os consumidores com filtro order_count' > 0 fazerem pedidos é: DOW_6 com um total de 22457 pedidos
O dia mais comum para os consumidores com filtro order_count' > 0 e percent_chain = 1 fazerem pedidos é: DOW_6 com um total de 6534 pedidos
O dia mais comum para os consumidores com filtro order_count' > 0 e percent_chain >= 0.5 fazerem pedidos é: DOW_6 com um total de 16007 pedidos Nada a destacar a ordem é sempre 6, 4, 5, 3, 2, 1, 0)

<BR><BR>

<section>

<details>

<summary><b style="font-size: 20px">Outras observações que estavão no Notebook</b></summary>

3. O output representa o percentual de pedidos feitos em restaurantes "chains" (redes de restaurantes) em cada hora do dia. Aqui está como interpretar os números:

HR_X: Cada linha corresponde a uma hora do dia. Por exemplo, HR_0 é meia-noite, HR_1 é 1 da manhã, e assim por diante até HR_23, que é 11 da noite.

Percentual: O valor ao lado de cada hora representa a porcentagem de todos os pedidos feitos naquela hora que foram em restaurantes chains.

Principais interpretações:
NaN para HR_0: Significa que não há dados ou pedidos feitos em chains à meia-noite (HR_0). Isso pode ser porque não houve pedidos a essa hora ou porque o cálculo não retornou um valor válido.

Picos de pedidos em chains: As horas com os maiores percentuais de pedidos feitos em chains são:

HR_19 (7 da noite): 76.16%
HR_20 (8 da noite): 79.11%
HR_21 (9 da noite): 76.21%
Isso sugere que, entre 7 e 9 da noite, uma grande parte dos pedidos é feita em redes de restaurantes.

Menores percentuais: As horas mais baixas (com exceção de HR_0, que tem NaN) estão nas primeiras horas da manhã:

HR_3 (3 da manhã): 52.57%
HR_4 (4 da manhã): 53.48%
Ou seja, nas primeiras horas da manhã, menos pedidos são feitos em chains em comparação com o horário de jantar.

Conclusão geral:
Durante o horário de pico das refeições (principalmente o jantar), uma maior porcentagem de pedidos é feita em redes de restaurantes. Já durante as primeiras horas da manhã, embora ainda haja uma presença significativa de pedidos em chains, ela é relativamente menor.

6. Análise de clientes extremos
Identifique os top 10 clientes com o maior número de pedidos em "chains" e veja se há um comportamento específico para esses clientes. Esses insights podem ser úteis para segmentar os clientes heavy-users de redes.

7. Razão de pedidos em chains versus independentes
Se houver outra variável que indique o número de pedidos feitos em restaurantes independentes, você poderia calcular a proporção entre pedidos em "chains" e independentes para cada cliente. Isso pode fornecer uma visão mais rica sobre a preferência de redes versus restaurantes locais.
Análise por Região (customer_region)
Análise por Idade (customer_age)

A variável is_chain pode ser explorada de diversas maneiras, principalmente para entender como os clientes interagem com restaurantes de redes (chains) em comparação com restaurantes independentes. Aqui estão algumas análises adicionais que podem ser feitas para aprofundar as informações já obtidas:

8. Comportamento de Compra ao Longo do Tempo (acho que não é possível)
Evolução dos Pedidos em Chains ao Longo dos Meses: Analisar se há uma tendência crescente ou decrescente de pedidos em chains ao longo dos três meses. Isso pode revelar mudanças sazonais ou de comportamento.
Intervalo entre Pedidos e Chains: Analisar o intervalo entre pedidos sucessivos de clientes que preferem chains em comparação com aqueles que preferem não-chains.

3. Análise de Preferência por Tipo de Culinária
Já vimos o gasto médio em diferentes tipos de culinária, mas podemos segmentar mais profundamente:
Comparar o número total de pedidos de cada tipo de culinária (e não apenas o gasto) entre chains e não-chains.
Analisar categorias específicas: Por exemplo, você mencionou um comportamento interessante em CUI_Chicken Dishes. Pode ser útil verificar a frequência com que pedidos de chicken dishes são feitos em chains, já que isso pode sugerir a dominância desse tipo de prato em redes de fast food.

4. Análise por Dia e Hora (Padrões Temporais)
Distribuição dos Pedidos por Dia da Semana: Verificar como a escolha por chains versus não-chains varia ao longo dos dias da semana. Já temos correlações, mas uma análise visual ou categórica (como percentuais de pedidos por dia) pode mostrar padrões mais claros.
Padrões Diários Específicos: Já vimos que as horas de jantar têm uma alta prevalência de pedidos em chains. Uma análise mais detalhada pode incluir a criação de categorias temporais, como “almoço”, “jantar”, e “madrugada”, para ver quais horários do dia mais influenciam a preferência por redes.

5. Análise de Promoções
Uso de Promoções e Preferência por Chains: Analisar se os clientes que utilizam promoções são mais propensos a fazer pedidos em chains. A variável last_promo pode ser cruzada com is_chain para verificar se redes de restaurantes são mais agressivas em oferecer descontos.
Promoção por Categoria de Produto: Identificar se as promoções são mais comuns em certos tipos de culinária e se isso afeta a escolha por chains.

6. Fidelidade e Frequência de Pedidos
Clientes que preferem Chains versus Frequência de Pedidos: Verificar se clientes que preferem chains fazem pedidos com mais frequência ou se os clientes que preferem não-chains têm uma frequência mais alta de pedidos.
Clientes Fieis a Chains Específicas: Se houver dados adicionais sobre os fornecedores, pode-se explorar se certos clientes pedem repetidamente de uma mesma chain, indicando um comportamento de fidelidade.

7. Análise por Método de Pagamento
Método de Pagamento e Chains: Explorar se os clientes que preferem chains tendem a usar certos métodos de pagamento mais frequentemente do que outros. Isso pode ajudar a identificar tendências em como os consumidores preferem pagar em restaurantes de rede (por exemplo, maior uso de aplicativos ou cartões de crédito).

8. Comparação com Variáveis Financeiras
Gasto Total: Comparar o gasto total de clientes que preferem chains com os que preferem não-chains. Isso pode ajudar a determinar se os clientes de redes gastam mais ou menos, em média.
Valor Médio por Pedido em Chains versus Não-Chains: Calcular o valor médio gasto por pedido em restaurantes chains e não-chains para ver se há uma diferença significativa.
Essas análises adicionais podem fornecer insights mais profundos sobre os hábitos dos clientes em relação a redes de restaurantes e como esses comportamentos são influenciados por outros fatores (como horário, tipo de culinária, promoções, etc.).

<BR>

</details>
</section>

<BR><BR>

<BR><BR>


>> Será que não faz sentido is_chain ser uma variável binária? (0 = não chain, 1 = pelo menos 1 chain)

--- 

# Filipa - `last_order` & `first_order`

> `first_order` & `last_order`

`FIRST_ORDER:`

Esta variável toma valores entre 0 e 90 e apresenta 106 missings (31782 obs)
Durante os 3 meses foi mais frequente os consumidores mandarem vir pela 1a vez nos dias:
0.0 __ 4.518281
1.0 __ 3.181046
6.0 __ 3.136996
2.0 __ 2.941917
3.0 __ 2.938770
7.0 __ 2.938770
5.0 __ 2.891574
50% 22.000000
75% 45.000000

(+ estatística)
Assimetria: 0.75 dist. pouco assimétrica à direita(+)
Curtose: -0.50 significa que a dist. tem menos dados em torno da média (menos picos) e mais dados nas caudas.
Média: 28.48
Variância: 581.248
Desvio padrão: 24.109

`LAST_ORDER:`

Esta variável toma valores entre 0 e 90 e não tem missings
Durante os 3 meses foi mais frequente os consumidores mandarem vir pela última vez nos dias:
89 __ 5.371927
88 __ 4.515805
84 __ 3.822755
87 __ 3.687908
83 __ 3.499749
86 __ 3.280231
25% 49
50% 70
75% 83

(+ estatística)
Assimetria: -0.93 dist. pouco assimétrica à esquerda(-) significa que a maioria dos dados está concentrada à direita da média e há alguns valores extremos à esquerda Curtose: -0.13 significa que a dist. é mais plana do que a distribuição normal, indicando uma dispersão menor dos dados em torno da média. Média: 63.68
Variância: 539.45
Desvio padrão: 23.22


<BR><BR>

---

#### `customer_region`

- As pessoas da região 2440 foram as que, em média, pediram pela 1º vez mais rápido


#### `customer_age`

> VER ISTO 


<BR><BR>

---

# Filipa - `last_promo`

```
Frequências absolutas:
-           16748
DELIVERY     6286
DISCOUNT     4496
FREEBIE      4358
Name: last_promo, dtype: int64
Moda: -

Frequências relativas (%):
-           52.521325
DELIVERY    19.712745
DISCOUNT    14.099348
FREEBIE     13.666583
Name: last_promo, dtype: float64
```

<BR><BR>

---

`order_count` & `last_promo`

>  Gráfico de Barras - Média de order_count por last_promo

>> Pq a média?


<BR><BR>

---

# Filipa - `last_promo`

df['group_1'] = df[['CUI_Asian', 'CUI_Japanese', 'CUI_Chinese', 'CUI_Thai', 'CUI_Noodle Dishes']].sum(axis=1)
df['group_2'] = df[['CUI_American', 'CUI_Street Food / Snacks']].sum(axis=1)
df['group_3'] = df['CUI_Italian']
df['group_4'] = df['CUI_OTHER']
df['group_5'] = df['CUI_Healthy']
df['group_6'] = df['CUI_Indian']
df['group_7'] = df['CUI_Chicken Dishes']
df['group_8'] = df[['CUI_Beverages', 'CUI_Desserts', 'CUI_Cafe']].sum(axis=1)

>>> Querem agrupar? [Decidir 🔴]

<BR><BR>

#### `last_promo` & `order_count`

```python
import scipy.stats as stats

# Executar ANOVA
anova_result = stats.f_oneway(*[df[df['last_promo'] == promo]['order_count'] for promo in df['last_promo'].unique()])
print(f"Resultado do teste ANOVA: F-statistic = {anova_result.statistic}, p-value = {anova_result.pvalue}")
```

Resultado do teste ANOVA: F-statistic = 253.54595731997887, p-value = 1.2793130981107255e-162

F-statistic: A estatística F compara a variação entre os grupos com a variação dentro dos grupos. Um valor F maior sugere que as diferenças entre os grupos são mais significativas em comparação com as variações internas dos grupos. Neste caso, o valor F é 253.55, o que é bastante elevado, sugerindo que há uma diferença significativa entre os grupos de last_promo em termos de order_count.

p-value: O valor-p indica a probabilidade de que as diferenças observadas entre os grupos sejam devidas ao acaso. Um p-value baixo (geralmente menor que 0.05) indica que há evidência suficiente para rejeitar a hipótese nula (de que não há diferença significativa entre as médias dos grupos). Aqui, o p-value é extremamente baixo (1.28e-162), o que significa que as diferenças entre os grupos de last_promo em relação a order_count são altamente significativas e é muito improvável que tenham ocorrido por acaso.

>> O que fazer com isto?


<BR><BR>



















