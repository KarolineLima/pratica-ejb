# pratica-ejb
Exemplo de EJB para disciplina Programação Distribuída.

## Prática:

### Altere o código da seguinte forma:
   Obs.: Ao final, você terá uma comunicação com fluxo da seguinte forma: Servlet -> Service -> DAO -> BancoDados

1. Crie uma classe de modelo, no mesmo pacote da classe Usuario, chamada Mensagem, que terá como atributos: id e texto (num design normal, teria ligação com Usuário. Porém, vamos simplificar aqui)
   * Marque a classe como @Entity e coloque o atributo id como sendo a chave primária com o @Id (ambas anotações da JPA, estando em import javax.persistence.)

2. Desenvolva a classe MensagemDAO, que será um EJB Stateless e terá um EntityManager injetado, similar à classe UsuarioDAO
    * A classe MensagemDAO deve ter os métodos inserir, listar e pesquisarPorId, que deve receber o id de uma mensagem como parâmetro e pesquisar apenas a mensagem do id especificado

3. Desenvolva a classe MensagemService, que será um EJB Stateless, e terá como nome para lookup sendo "mensagemService": @Stateless(name = "usuarioService")
    * Olhe a classe UsuarioService e veja as anotações necessárias
    * Crie o atributo MensagemDAO, que será injetado via a anotação @EJB, para que você o use para realizar as operações no banco de dados

4. Desenvolva um servlet, similar ao UsuarioServlet, chamado MensagemServlet, que será o cliente do serviço de mensagens

5. Altere o index.html para ter as operações sobre mensagens, chamando apropriadamente o MensagemServlet

