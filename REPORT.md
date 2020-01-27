
## (Melhoria do) Relatório do Trabalho 1

### Identificação e exploração das vulnerabilidades

* **SQL Injection**
O site era vulnerável a ataques por SQL Injection.
Esta vulnerabilidade permite-nos inserir código SQL em campos de formulário do site, ou através do URL.
Através disso, podemos inserir códigos para ultrapassar controlos de acesso, como o login, ou inserir queries diferentes no sistema, para obter informação como tabelas de sistema, outras tabelas importantes...
Podemos, ainda, inserir novos ficheiros no sistema, dependendo das permissões de escrita do utilizador da base de dados.

* **Cross-site scripting (XSS)**
A vulerabilidade a cross-site scripting permite inserir código, agora javascript, em campos do site.
O código inserido pelo atacante pode executar várias ações, com diferentes objetivos, dividindo os tipos de ataque por XSS em várias categorias:
  1. **Não persistente (refletido)**, no qual o código inserido pelo atacante não é armazenado em nenhum lado, mas apenas refletido na página, podendo realizar diversas ações. Neste caso, o atacante pode enviar um link contendo uma query maliciosa que, inserindo este conteúdo na página, será executado no browser do cliente.
  2. **Persistente (armazenado)**. Este ataque consiste em armazenar código javascript no servidor da página web, quie será apresentado em todas os clientes que consultarem a página. Pode ser explorado num campo de *Comentários*, *Questionários*, *Posts*, etc., onde possamos introduzir o código, de forma a que seja apresentado em outros sítios. No caso **desta página**, era esta a variante de XSS que podíamos explorar.
  Existem ainda outros tipos de ataques XSS, como **XSS Server side**.

Estas foram as principais vulnerabilidades que encontramos no sistema e tentamos explorar.

* **Más configurações**
Além das vulnerabilidades conhecidas que encontramos, notamos algumas más configurações no sistema que, sendo evitadas, poderiam evitar mais ataques.

Em primeiro lugar, o facto de o servidor da base de dados estar exposto apresenta um risco, que poderia ser evitado uma vez que, tendo acesso remoto ao servidor em si, não há necessidade de ter o servidor da BD aberto.

Por outro lado, o facto de o servidor SSH aceitar autenticação por password apresenta o risco de ataque por força bruta. Deveria aceitar apenas autenticação por pares de chaves SSH.


