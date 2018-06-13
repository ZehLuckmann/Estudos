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
<!--stackedit_data:
eyJoaXN0b3J5IjpbODExNTc5NDk2LDUwNzg2NDI4OSwtMTAzMz
EyNzg0LC0yMDg0MDUwNjc4LDE2NjkwMTg4NTcsMjMyMTcxMzEz
XX0=
-->