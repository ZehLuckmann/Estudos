# Comandos de Relatórios - Criando Visualizações

Ao obter valores estatísticos, é possível exibir estes resultados em diversos formatos

## Line Charts
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```

## Area Charts
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTMzNzU0MTYsLTIwODQwNTA2NzgsMTY2OT
AxODg1NywyMzIxNzEzMTNdfQ==
-->