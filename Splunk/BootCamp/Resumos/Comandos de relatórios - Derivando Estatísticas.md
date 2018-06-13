# Comandos de Relatórios - Derivando Estatísticas 
## Reporting Commands
Nesse módulo você vai aprender sobre os seguintes comandos:
* _top_ - A busca mostra os registros mais comuns, na ordem decrescente da contagem
* _rare_ - A busca mostra os registros menos comuns, na ordem crescente da contagem
*  _stats_ - Calcula as estatísticas nos eventos que coincidem com seus parâmetros de pesquisa

### Comando _top_ e _rare_
O comando _top_ busca os valores mais comuns do seu resultado, enquanto o _rare_ busca os resultados mais incomuns :
*  Por padrão exibe os registros em forma de tabela
* Automaticamente retorna as colunas de contagem e porcentagem
* Adicionando `limit=#` depois do comando _top_, retorna um numero específico de resultados
	* Por padrão, 10 registros são exibidos
	* `limit=0` remove o limite de registros
Exemplos:

	sourcetype=linux_secure password fail*
	| top src
	
	sourcetype=acess_combined action=purchase
	| top product_name

	sourcetype=acess_combined action=purchase
	| top host, product_name limit = 3 countfield= "Units Sold" showperc=f

	sourcetype=acess_combined action=purchase
	| top product_name by host limit = 3 countfield= "Units Sold" showperc=f

	sourcetype=cisco_wsa_squid
	| rare sowperc=0 limit=1 s_hostname 
		
### Comando _stats_
* _stats_ permite que você calcule estatísticas em cima dos registros que corresponderem a sua consulta
* As funções mais comuns são:
	* _count_ - Conta o número de eventos que corresponde a consulta
	* _distinct_count_, _dc_ - Retorna a contagem dos valores únicos do campo informado
	* _sum_ - Soma os valores de um campo numérico
	* _avg_ - Retorna a média de um campo numérico
	* _list_ - Lista todos os valores de um campo específico
	* _values_ Lista valores exclusivos de um determinado campo

#### _count_
* Retorna o número de eventos baseado no critério de pesquisa informado
* Use a clausula _as_ para renomear o campo de conta
* Adicionando o argumento field ao comando _count(field)_, retorna o número de eventos deste campo
* Para contar valores específicos de um determinado campo, use _count_ junto com a função _eval_
	* Exige uma clausula _as_
	* Aspas duplas são necessárias para o valor do campo
	* Valor do campo é case-sensitive
Exemplos:
		sourcetype=vendor_sales
		|stats count

	sourcetype=vendor_sales
	|stats count as "Number of Retail Store Purchases"

	sourcetype=acess_combined
	| stats count(action) as ActionEvents,
	count as TotalEvents
	
	sourcetype=acess_combined action=*
	| stats count(eval(action="view")) as Views,
	  count(eval(action="purchase")) as Purchases

#### 	_by fields_
* A cláusula _by_ retorna uma contagem para um campo ou grupo de campos
Exemplo:

		sourcetype=vendor_sales
		| stats count as quantify by product_name, price


#### _distinct_count(field)_ ou _dc()_
*  Fornece uma contagem de quantos valores exclusivos existem para um dado campo no conjunto de resultados
Exemplo: 

		sourcetype=cisco_wsa_squid
		| stats dc(s_hostname) as "Websites visited"
		
#### _sum(field)_
* Para campos que contenham um valor numérico, você pode usar para somar
Exemplo:

		sourcetype=cisco_wsa_squid
		| stats sum(sc_bytes) as Bandwidth by s_hostname
		| sort -Bandwidth

#### _avg(field)_
* Retorna a média de um determinado campo numérico
Exemplo:
		
		sourcetype=cisco_wsa_squid
		| stats avg(sc_bytes) as "Average Bytes"
		 by usage
		 
#### _list(field)_ e _values(field)
* _list_ Lista todos os valores para um campo especifico
* _values_ Lista os valores únicos para um campo específico
Exemplo:
		sourcetype=cisco_wsa_squid
		| stats list(s_hostname) as "Websites visited: "
		  by cs_username

### Comando _sort_
* Use para ordenar os seus resultados
* Use o parâmetro + para crescente(padrão) ou - para decrescente 
* Para limitar os resultados use a opção `limit`
Exemplo:

		sourcetype=vendor_sales
		| dedup Vendor
		| table VendorCountry, VendorStateProvince, VendorCity, Vendor
		| sort - VendorCountry, +VendorStateProvince, VendorCity, Vendor

### Comando _addcoltotals_
* Faz a soma de todos os campos numéricos do seu conjunto de resultado
	* Adiciona um totalizador no final da coluna
	* Para um nome para a linha use `labelfield=<field>`
	* Se nenhum campo for especificado, todos os campos serão totalizados
	* Para selecionar quais colunas você deseja totalizar use : `addcoltotals field1, field2, field3`
Exemplo:

		sourcetype=acess_combined
		| stats sum(bytes) as totalBytes,
		| avg(bytes) as avgBytes,
		count as totalEvents by host
		| addcoltotals totalBytes, totalEvents
	      labelfield=host label=TOTALS
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzODA4NTQwMDEsOTIwODI0NzExLDEwNT
k5OTY0ODIsOTgwODEwNTQ3LDcwOTk5NTc1N119
-->