# Comandos de Relatórios - Criando Visualizações

Ao obter valores estatísticos, é possível exibir estes resultados em diversos formatos

## Gráfico de linha
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
![enter image description here](https://lh3.googleusercontent.com/1Hv4AyKg4RAx0LHF7So6anJNZD1cnh98_62cCyL2B5JRyRLzyRlllxD5BFuv9ZaCGWEFR8VZif8bCg)
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```

## Gráfico de Área
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```

## Gráfico de Colunas
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```

## Gráfico de Barras
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```

## Gráfico de Pizza
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
eyJoaXN0b3J5IjpbMTA3MDkyMTc0NSwtMTk1NDQ2ODM5MiwtMT
A3OTE0NTA4Miw4MTE1Nzk0OTYsNTA3ODY0Mjg5LC0xMDMzMTI3
ODQsLTIwODQwNTA2NzgsMTY2OTAxODg1NywyMzIxNzEzMTNdfQ
==
-->