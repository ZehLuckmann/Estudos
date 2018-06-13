# Comandos de Relatórios - Derivando Estatísticas 

## Reporting Commands

Nesse módulo você vai aprender sobre os seguintes comandos:
* _top_ - A busca mostra os registros mais comuns, na ordem decrescente da contagem
* _rare_ - A busca mostra os registros menos comuns, na ordem crescente da contagem
*  _stats_ - Calcula as estatísticas nos eventos que coincidem com seus parâmetros de pesquisa

### Comando _top_

O comando _top_ busca os valores mais comuns do seu resultado:
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


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYyMTUwMzc2OSw3MDk5OTU3NTddfQ==
-->