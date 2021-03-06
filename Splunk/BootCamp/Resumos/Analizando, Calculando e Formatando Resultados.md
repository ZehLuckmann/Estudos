# Analizando, Calculando e Formatando Valores

## Comando _eval_

* _eval_ permite que você calcule e manipule valores no seu relatório
	* Útil para cálculos como adição, subtração, multiplicação e divisão
	* Não sobrescreve os dados no index
* Suporta uma variedade de funções
*  Os resultados do _eval_ são escritos em um campo especificado
	* Pode ser um campo novo ou um já existente
	* Se o campo de destino existir, a informação é substituída pelo resultado do _eval_
	* Os valores dos campos são tratados de forma case-sensitive
* O comando _ eval te permite:
	* Calcular expressões
	* Colocar um valor em um campo
	* Usar o campos da pesquisa ou outras expressões
* Tipo de operadores
	* Aritméticos:  + - * / %
	*  Concatenação: + .
	* Condicionais: AND OR NOT XOR < > <= >= != = == LIKE
#### Exemplo: Convertendo valores
Obter os valores de consumo de banda em bytes é difícil, o ideal é converter o mesmo para uma unidade como o megabyte
```
sourcetype=cisco_wsa_squid
| stats sum(sc_bytes) as Bytes by usage
| eval bandwith = round(Bytes/(1024*1024), 2)
| sort -bandwidth
| rename bandwidth as "Bandwidth (MB)"
| fields - Bytes
```
#### Exemplo: Calculando valores

Calcular o preço real de um produto e o seu preço na promoção e exibir os valores de porcentagem de desconto
```
sourcetype=acess_combined product_name=* action=purchase
| stats sum(price) as total_list_price,
  sum(sale_price as total_sale_price by product_name
| eval discount = round((total_list_price - total_sale_price)/total_list_price)*100)
|sort -dicount
|eval discount = discount."%"
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MjgyOTg5MzksMTEyOTMzNjUzNSwxOT
g4Njc4NTgwXX0=
-->