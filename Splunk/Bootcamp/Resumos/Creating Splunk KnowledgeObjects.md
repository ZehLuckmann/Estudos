# Fundamentos de Pesquisa

## Pesquisa Básica

* __Palavras chaves__
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

# Práticas Gerais de Pesquisa

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
