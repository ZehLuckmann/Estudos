# Fundamentos de Pesquisa

## Pesquisa Básica

* __Palavras-chaves__
    Retorna os registros que tenham incidencia da palavra, por exemplo pesquisar por 'Erro'
* __Frases__
    Retorna os registros que tenham incidencia da frase, por exemplo pesquisar por 'Erro Fatal' (é diferente de pesquisar por 'erro AND fatal')
* __Campos__
    Procura campos que satisfaçam uma determinada condição, por exemplo 'codigoErro=404'
* __Condicionais__
    OR, AND, NOT; AND já fica implícito; você pode usar ()'s para priorizar operações; Lembrando que os operadores devem estar em maiúsculo
* __Curingas__
    Por Exemplo 'codigoErro=40*', retorna 401, 403, etc.; Evite usar *40, é muito ineficiente
* __Comparações__
    Operações entre dois valores(=,!=,<,<=,>=.>)

## Práticas Gerais de Pesquisa

* Tempo é o filtro mais eficiente
* Quanto mais você informar para a pesquisa, maior as chances de se obter bons resultados
    * Procurar por 'Acesso negado' é sempre melhor que procurar por 'negado'
    * Para a pesquisa se tornar mais eficiente, inclua o máximo de termos possíveis
        * Se você deseja encontrar eventos que contenham 'erro' e 'sshd' e 90% dos eventos incluem erro, mas apenas 5% 'sshd', inclua ambos os termos na pesquisa
* Inclusão geralmente é melhor que a exclusão
    * Procurar por "Acesso negado" é mais rápido que pesquisar por NOT 'Acesso autorizado'
* Aplique os maiores filtros o mais cedo possível na sua pesquisa
    * Filtrar 1000 registros, remover duplicados e ordenar é mais rápido que filtrar 1000 registros, ordenar e remover os duplicados

## Conceitos de sintaxe da linguagem de pesquisa

Pesquisas são formadas basicamente de 5 componentes

* __Termos de pesquisa__ - O que você está procurando?
    * Palavras-chaves, frases, condicionais, etc.
* __Comandos__ - O que você deseja fazer com estes resultados?
    * Criar um gráfico, computar estatísticas, calcular, formatar, etc.
* __Funções__ - Como você espera esse gráfico, cálculo, etc.
    * Obter uma soma, uma média, trasformar os valores, etc.
* __Argumentos__ - Quais váriaveis que você deseja aplicar esta função?
    * Calcular a média de um campo específico, converter milisegundos para segundos, etc.
* __Clausulas__ - Como você deseja agrupar ou chamar os campos no resultado?
    * Renomear um campo, ou agrupar os valores a partir de determinado campo

#### Exemplo de pesquisa:
```
sourcetype=acess_* status=503 | stats sum(price) as lost_revenue | fieldformat lost_revenue = "$" + tostring(lost_renevue, "commas")    
```

```
sourcetype=linux* failed password | top user | fields - percent
```

### Comando _fields_

* Extração de campos é uma das etapas que mais exige da pesquisa
* O comando _fields_ permite você incluir ou excluir campos especificos da sua pesquisa ou relatório
* Para incluir, use _fields_ (+ está implícito)
    * Ocorre após a extração de campos
    * Melhora a performance, porque apenas os campos informados são extraídos
* Para excluir, use _fields -_
    * Ocorre após a extração de campos
    * Não melhora a performance
    * Exclui os campos usados na pesquisa, para tornar mais fácil de ler
* _fields_ não inclue os campos internos (_raw, _time)
