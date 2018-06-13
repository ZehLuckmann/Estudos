# Comandos de Relatórios - Criando Visualizações

Ao obter valores estatísticos, é possível exibir estes resultados em diversos formatos

## Line Charts
```
sourcetype=acess_combined action=purchase
| chart count(product_name) by categoryId
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwODQwNTA2NzgsMTY2OTAxODg1NywyMz
IxNzEzMTNdfQ==
-->