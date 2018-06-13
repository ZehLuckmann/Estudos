
# Exercício 2 - Fundamentos de pesquisa

### Descrição

Estes exercícios vão utilizar os comandos _fields_, _table_, _erex_ e _multikv_. 

### Passo a passo 
Cenário: Verifique se há problemas com compras de clientes na loja on-line.

Exemplo de resultado final: 
Customer IP | Web Server | HTTP Status 
--------------|------------|------------- 
142.162.221.28|www1 |404 
12.130.60.5 |www3 |
503 27.96.191.11 |www2 |500

1. Pesquise transações on-line `sourcetype = access_combined`
	* Use o comando _table_
	* Exiba apenas os campos clientip, host, action e status.
	
		
clientip | host | action | status
---------|------|--------|-------------
125.7.55.180|www3|addtocart|200
125.7.55.180|www3|purchase|200
125.7.55.180|www3|view|200	
125.7.55.180|www3||200
84.34.159.23|www1|purchase|200
84.34.159.23|www1|purchase|200
84.34.159.23|www1|addtocart|200
	
	Resultado: 
	<Escreva sua consulta aqui>
2. Filtrar para exibir apenas os campos com a ação de comprar `action=purchase`, e não mostrar a coluna 'action':
	
clientip | host | status
---------|------|--------|--------
125.7.55.180|www3|200
84.34.159.23|www1|200
84.34.159.23|www1|200
	
	Resultado: 
	<Escreva sua consulta aqui>
3. Torne os dados mais apresentáveis definindo um título para as colunas

Custommer IP | Web Server | HTTP Status
---------|------|--------|--------
125.7.55.180|www3|200
84.34.159.23|www1|200
84.34.159.23|www1|200
	
	Resultado: 
	<Escreva sua consulta aqui>

4. Modifique a consulta para retornar os valores com o `status > 399`

Custommer IP | Web Server | HTTP Status
---------|------|--------|--------
125.7.55.180|www3|503
84.34.159.23|www1|400
	
	Resultado: 
	<Escreva sua consulta aqui>
5. Salve sua pesquisa como um relatório L2S1
6. Na opção __Save As__ do menu, selecione __Dashboard Panel__
7. Salve o dashboard com estes valores
	* __Dashboard__: New
	* __Dashboard Title__: IT Ops
	* __Panel Title__: Server Errors
	* __Panel Powered by__: Inline Search
	* __Panel Content__: Statistics   
	
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc0NzIxNTc1MSwtMTIxNzcwOTIxMywtMT
M1MTI0NzkwNV19
-->