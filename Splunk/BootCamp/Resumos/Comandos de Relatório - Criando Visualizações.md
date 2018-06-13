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
![enter image description here](https://lh3.googleusercontent.com/QgRpUuVI-5Sz6nD770RVCNkKIeFmOXCZsnBEcb-WOFQ3JbMIVof1cdvjHasQqHEKGVwul2DySlgsFQ)
## Gráfico de Área
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
![enter image description here](https://lh3.googleusercontent.com/EEQ-H5meTFSyJf4LtnZAZyUwUrvypoz-PVetd-WLSwdDx3BJI8WPY8wJFMrzAu8sSJ0cPFNsvT__fg)
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```
![enter image description here](https://lh3.googleusercontent.com/4PhJcDdXobmnSBEmUYl-u4_fFFrcMRMpIAdlqhkgfMvTZ00A73aP2joZoTu3yIU0GH89CTqQXkohKQ)
## Gráfico de Colunas
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
![enter image description here](https://lh3.googleusercontent.com/MN5iynfuK6uhAjC0IrJ27bDmY5YVZttFLXSh7AiGs3ghnRa9-EpDem8l_dwfuW0MaFc7tiL887acHA)
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```
![enter image description here](https://lh3.googleusercontent.com/IMaerquOmLImsR4ODD3uFRo6-XtBDlqXDQt9XgbbKhqsvw4Ahe1MyT00XcqNbENEpWAnaHfEiD-vGQ)

## Gráfico de Barras
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
![enter image description here](https://lh3.googleusercontent.com/RaVAFvWzHitJaZbmYQiXK3UQs-gMP76N7z9dtNxP9fiVBaCSoJLgOlBUYXeb0EBMTHkdLvCxr5QEyw)
```
index="buttercupgames" action=purchase 
| timechart count(productId) by categoryId
```
![enter image description here](https://lh3.googleusercontent.com/PLHt9kmad9FkQxvc3YNZsk7wop-0h-j9xXiY44MFRHgurIaxz8NTG8n8GI2NqRG1wxAPeZLVMLWlqQ)
## Gráfico de Pizza
```
index="buttercupgames" action=purchase 
| chart count(productId) by categoryId
```
![enter image description here](https://lh3.googleusercontent.com/jQYoMCi37PP-El7ZmyqTrRftjOmASolP2RAtFkLWo2FwCjrBoWjtcG7RFGVAQy6s-4bK9ahPZKdU2A)
## Visualização de valores únicos
```
index="buttercupgames" "action=purchase"
| stats sum(bytes) as count
| gauge count 500000 10000000 20000000 25000000
```
![enter image description here](https://lh3.googleusercontent.com/Wo1WRy_-Yrj2VxtxV4TXRqznguHCVy6SUek9Ncpgrfjdc17JREiu8rUelgoX6CKmOz5A9J1fEQe__A)![enter image description here](https://lh3.googleusercontent.com/EoiNLYB4GDoal4alaxQ1nTVxYMbLtWvt8wiBYgG88NW-Rqp8KINY4i2b1y7GmVlw61QNsIrwsARhLw)![enter image description here](https://lh3.googleusercontent.com/Z5OUF2n-mH-auklrE-c6dj6eMlvL-pQeBEnajWVw7Vkwpz1uAjaVe8D7-RsWGu04iy_950FRoR6iSA)![enter image description here](https://lh3.googleusercontent.com/1vfwygd5o-pQUV6zUclHwE658y-Bz0df2Up1GfT10z_E_vUkiKxoEJP-TlGKOl9XJRhJwwhPigPljw)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NzcyNTQwNTUsLTE5NTQ0NjgzOTIsLT
EwNzkxNDUwODIsODExNTc5NDk2LDUwNzg2NDI4OSwtMTAzMzEy
Nzg0LC0yMDg0MDUwNjc4LDE2NjkwMTg4NTcsMjMyMTcxMzEzXX
0=
-->