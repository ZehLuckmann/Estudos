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

## Column Charts
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```

## Bar Charts
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```

## Pie Charts
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
## Visualização de valores únicos
```
index="buttercupgames" "action=purchase"
| stats sum(bytes) as count
| gauge count 500000 10000000 20000000 25000000
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAwMDk3MDI4Miw4MTE1Nzk0OTYsNTA3OD
Y0Mjg5LC0xMDMzMTI3ODQsLTIwODQwNTA2NzgsMTY2OTAxODg1
NywyMzIxNzEzMTNdfQ==
-->