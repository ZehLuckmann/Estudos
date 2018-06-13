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
eyJoaXN0b3J5IjpbLTE3Njc4OTgwMzUsODExNTc5NDk2LDUwNz
g2NDI4OSwtMTAzMzEyNzg0LC0yMDg0MDUwNjc4LDE2NjkwMTg4
NTcsMjMyMTcxMzEzXX0=
-->