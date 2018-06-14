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
1. Calcular o numero de bytes por tipo de uso
2. Criar um novo campo chamado `bandwidth`
3. Converter o valor de Bytes para MB, dividindo o campo por (1024*1024)
4. Arredondar o 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NDM4ODA1NDMsMTkyNTg1NDM1MywtMT
k5MTI2ODUzNywxOTIzNDMzOTg3LDEwNjg0MzYzMTMsLTE1NzQx
MDI0ODhdfQ==
-->