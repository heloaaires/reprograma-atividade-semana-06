# On16-TodasEmTech-s6-Intro-API-Node
Turma Online 16 | Back-end | 2022 | Introdução à API:
HTTP e NodeJS

## Para casa
1) Qual a relação entre os métodos HTTP e o CRUD?

CRUD é um acrônimo para os verbos que representam as 4 operações básicas que usamos em um banco de dados relacional, quais sejam: Create, Read, Update and Delete (Criar, Consultar, Atualizar/Modificar, Excluir).
Seguindo a semântica dos verbos no acrônimo CRUD, podemos relacionar os métodos HTTP da seguinte forma: 
Create --> Post : O método POST é utilizado quando queremos *criar* um recurso. Quando usamos POST, os dados vão no corpo da requisição e não na URI.
Read --> Get : Através dessa requisição nós pedimos a representação de um recurso: que pode ser um arquivo html, xml, json, etc.
Update --> Patch : Serve para *atualizar* partes de um recurso, e não o recurso todo.
Delete --> Delete : Exclui o recurso especificado.

2) Comente, com exemplos, a diferença entre o PUT e o PATCH.
O PUT é utilizado para alterar completamente um dado, enquanto que o PATCH é usado para modificá-lo parcialmente. Por exemplo, se em um cadastro temos os seguintes dados: nome, CPF e endereço e o usuário deseja alterar todos os campos, utilizamos o PUT que -supondo a partir da semântica- seria como enviar (pôr) novamente a informação naquele banco de dados. 
Se o usuário deseja apenas modificar um campo mno seu formulário de dados, usaríamos o PATCH, que na tradução significa "remendo, conserto", ou seja, seria uma correção de algum dado. 

3) As respostas da questão 3 está no arquivo script.js de cada exemplo. Confesso que não entendi muito bem o que foi solicitado no enunciado das questões. :-) Espero que esteja certo. 

4) Defina o conceito de idempotência e como uma API pode ser idempotente
A idempotência é uma características dos métodos onde o resultado de uma requisição realizada com sucesso é independente do número de vezes que é executada. Ou seja, uma requisição idêntica pode ser feita uma ou mais vezes em sequência produzindo o mesmo efeito, deixando o servidor no mesmo estado. Uma API pode ser idempotente se ela utiliza apenas os métodos idempotentes do protocolo http, que são: GET, PUT, DELETE, HEAD e OPTIONS são idempotentes. Esses métodos, depois de chamados pela primeira vez, não aletaram o estado atual do servidor.
POST não é idempotente porque sua principal função é criar um novo recurso, então a cada vez que ele é chamado, ele cria um novo recurso e altera o estado atual do servidor. O PATCH também não é idempotente porque a cada chamada ele pode modificar um campo dos dados, por exemplo. Na chamada 1, ele modifica o nome. Na chamada 2, ele deixa o mesmo valor pro nome, mas modifica o endereço, etc. Esse comportamento é diferente do PUT já que nesse método o valor é alterado, mas na chamda seguinte ele permanece igual. Por exemplo, você atualiza o campo do nome, e na chamada seguinte o nome permanece alterado. 

5) Cite alguns diferentes padrões de projetos de software
Padrões de projetos são modelagens que podemos seguir ao desenvolver um código em busca de uma solução específica para nosso problema. Os padrôes devem atender aos seguintes princípios, que em inglês, formam o acrônimo SOLID: 
S” Single Responsibility Principle (Princípio de responsabilidade única): uma classe deve ter uma e apenas uma razão para mudar.
“O” Open-Closed Principle (Princípio aberto/fechado): objetos devem estar disponíveis para extensão, mas fechados para modificação.
“L” Liskov Substitution Principle (Princípio de substituição de Liskov): uma subclasse deve ser substituível por sua superclasse.
“I” Interface Segregation Principle (Princípio de segregação de interface): uma classe não deve ser obrigada a implementar métodos e interfaces que não serão utilizadas.
“D” Dependency Inversion Principle (Princípio de inversão de dependência): dependa de abstrações e não de implementações.
Os padrões de projetos foram classificados de acordo com a natureza do problema que desejam solucionar, sendo de 3 tipos:
A) Padrões criacionais: estes padrões oferecem diversas alternativas de criação de objetos, o que aumenta a flexibilidade e a reutilização de código. 
B) adrões estruturais: Nos mostram como montar objetos e classes em estruturas maiores, sem perder a eficiência e flexibilidade.
C) Padrões comportamentais: Nos ajudam a trabalhar melhor com os algoritmos e com a delegação de responsabilidades entre os objetos.

Referências: 
1. Design Patterns: breve introdução aos padrões de projetos. Disponível em: <https://www.alura.com.br/artigos/design-patterns-introducao-padroes-projeto?gclid=CjwKCAjwjtOTBhAvEiwASG4bCEcMjMu1anmaHEVMoX2zo0jTdb8Dq8UUrfJ8BQbylp42CGKEibzvdhoCofYQAvD_Bw>
2. API Restful: boas práticas. Disponível em: <https://www.brunobrito.net.br/api-restful-boas-praticas/>
3. O que é idempotencia e porque devemos utilizar. Disponível em: <https://xuenqui.medium.com/idempot%C3%AAncia-uma-boa-pr%C3%A1tica-a-se-utilizar-em-servi%C3%A7os-rest-633c38f4d7c0>
4. Idempotente. Disponível em: <https://developer.mozilla.org/pt-BR/docs/Glossary/Idempotent>
5. PUT vs. PATCH: Pare agora de escolher o errado. Disponível em: <https://medium.com/@gabrielrufino.js/put-vs-patch-pare-de-agora-escolher-errado-533b8c6058d9>
