Prova AB1, Projeto de Software, dia 20/02/2019
Victor Mafra de Holanda Ferraz
Engenharia de Computação


- **Funcionalidades**:

  - **Adição de usuário ao laboratorio**: Ultilizei um HashMap para armazenar os Usuários no sistema, pois cada usuário é único, ultizando o seu nome como chave e o próprio usuário como dado;
  - **Adição e remoção de informações referentes aos projetos/atividades**: Ultilizei um HashMap para armazenar as informaçoes extras que o usuário deseja adicionar, ultilizando o que a informação é como chave e a informação em si como dado.
  Foi criado um metodo chamada AddInformação() e outra chamada RemoverInformação() para permitir que esta funcionalidade seja acessada;
  - **Associação de usuário**: Ultilizei um HashMap na Classe Projeto para armazenar os participantes do projeto, pois cada usuário é único, ultilizando seu nome como chave e o proprio usuario como dado.
  Nesta mesma classe, existe um metodo chamado AddMembro(Usuário x) que permite que o coordenador do projeto aloque participantes ao projeto;
  - **Alteração de Status**: Para cada alteração de status, o sistema verifica se as informações necessárias para a alteração foram satisfeitas, caso tenham sido, o status do projeto é atualizado.
  Foram criados tres metodos para esta funcionalidade: IniciarProjeto(), que verifica se as informações básicas foram fornecidas e alterar o status do projeto para "iniciado",
  TerminarAlocação(), que verifica se existem usuários alocados no projeto e muda o seu status para "em andamento", não permitindo mais que nenhum usuario seja alocado,
  ConcluirProjeto(), que verifica se existem atividades relacionadas ao projeto e altera seu status para concluido, assim não permitindo mais que ele seja gerenciado pelo coordenador;
  - **Consultas**: Para esta funcionalidade, foram criados métodos que existem nas Classes Usuário, Projeto e Atividade.
  Estes métodos são: PrintProjetos(): está na classe Usuário e printa o nome de todos os projetos ao qual o usuário consultado faz parte, atraves do metodo keyset() da coleção Map e do metodo toArray() da coleção Set.
  PrintAtividades(): também esta na classe Usuario e printa o nome de todas as atividades ao qual o usuario participor, ultilizando os mesmo principio da anterior,
  PrintAtividadesResponsável(): ainda na classe Usuario, printa o nome de todas as atividades ao qual o usuario foi responsavel, ultilizando o mesmo conceito explicado anteriormente,
  PrintProjetosCoordenados(): agora na sub-classe Coordenador, printa o nome de todos os projetos ao qual o usuario foi coordenador, ultilizando a mesma tecnica,
  PrintMembros(): contido na classe Projeto, printa o nome de todos os membros do projeto,
  PrintAtividades(): contido ainda na classe Projeto, printa o nome das atividades relacionadas ao projeto consultado,
  PrintCoordenaor(): printa o nome do coordenador do projeto consultado,
  PrintInfo(): printa todas as informações referentes ao projeto consultado, incluindo as adicionas que o usuário adicionou após a criação,
  PrintMembros(): contido na classe Atividade, printa o nome de todos os membros que participaram da atividade,
  PrintReponsável(): printa o nome do responsável pela atividade;
  PrintProjeto(): printa o nome do projeto ao qual a atividade consultada esta relacionada;
  - **Gerar Relatório**: Para esta funcionalidade, o metodo GerarRelatorio(), contido na Classe Laboratorio, foi criado, este metodo printa o nome de todos os contribuintes do laboratorio, todos os projetos criado, todas as atividades feitas, etc.
  Ultilizando da mesma tecnica citada anteriormente, atraves dos metodos keySet() e toArray(), das coleções Map e Set, respectivamente.
  
- **Classes**:
  
  - **Laboratório**:
  
    - **Motivação**: Era necessária a criação de uma classe que fosse a central do sistema, funcionando como o sistema em si, onde seriam armazenadas todas as informações.
    - **Solução**: Foi entao criada a classe Laboratório, que contem todos os usuário adicionados ao laboratorio, todos os projetos criados e atividades criadas.
    - **Vantagens**: A criação desta classe permite que o programador tenha um local que sirva de sistema operador do programa, podendo adicionar tudo que precisa nesta classe, servindo como a parte principal do programa.
    - **Desvantagen**: Não vejo nenhum desvantagem clara da criação desta classe.
    
  - **Usuário**:
  
    - **Motivação**: O sistema foi pensado em volta de usuário do laboratorio, então era mais que necessária a criação de uma classe onde seriam armazenados o nome, a senha de login do usuário, os projetos participados, etc.
    - **Solução**: Foi criada a classe Usuário, que contem exatamente o que era necessário, o nome, senha, projetos, atividades, tudo que era necessário de se saber sobre cada contribuinte do laboratorio. Esta classe abrange tais usuários: Alunos me geral, profissionais e tecnicos.
    - **Vantagens**: Por ser uma Super Classe, ela permite a criação de sub-classes para evitar a repetição de atributos nas classes, além de ser impossivel a efetuação do sistema sem uma classe como essa.
    - **Desvantagens**: Sem desvantagens claras, ao meu ver.
    
  - **Coordenador**:
  
    - **Motivação**: Era necessária a criação de uma sub-classe da classe Usuário, a qual poderia ser coordenadora de projetos, abrangindo assim os usuários professor e pesquisador do laboratorio.
    - **Solução**: Foi criada a sub-classe Coordenador, que contém todas as informações da Super Classe Usuario, além tambem dos projetos ao qual o usuário é coordenador.
    - **Vantagens**: Permite que a verificação se o usuário pode ou não ser coordenador de um projeto seja muito mais simples, apenas ultizando a verificação de instancia, além de evitar que atributos desnecessarios fossem criados, onde nem todos os usuário iriam preencher tal atributo.
    - **Desvantagens**: Deve existir uma maneira mais eficiente de se fazer o que era necessário sem a criação desta sub-classe, porém foi a melhor solução que consegui pensar no momento.
    
  - **Projeto**: 
  
    - **Motivação**: Era necessária a criação de uma classe que representasse os projetos em si.
    - **Solução**: Foi criada a classe Projeto, que contém todas as informações básicas do projeto, além dos membros do projeto e das atividades relacionadas, assim como os métodos que permitem que o projeto seja gerenciado pelo seu coordenador.
    - **Vantagens**: Era extremamente necessária a criação de uma classe como esta.
    - **Desvantagens**: Talvez a criação de uma super classe que englobasse tanto a classe projeto como a classe atividade fosse mais eficiente.

  - **Atividade**:
  
    - **Motivação**: Mesmo caso da classe Projeto, era necessária a criação de uma classe que representasse as atividades.
    - **Solução**: Foi criada a classe Atividade, contendo as informações básicas sobre a atividade e os metodos necessário para seu gerenciamento.
    - **Vantagens**: As vantagens são as mesmas da classe anterior.
    - **Desvantagens**: As desvantagens são as mesmas da classe anterior.

- **Distribuição de métodos (Apenas os principais metodos)**:
  
  - **Login**(): Este método so poderia ser colocado na Classe Usuário pois é nesta classe que estão armazenados todos os usuários do laboratorio;
  - **GerenciarProjeto()**: Este método poderia ser colocado tanto na Classe laboratório como na sub-classe Coordenador, resolvi por em Laboratório pois é nessa classe que estão armazenados todos os projetos criados, assim sendo mais fácil a verificação;
  - **GerenciarAtividade()**: Este metodo poderia tamber ser colocado tanto em laboratorio quanto em Usuário, mas foi posto em laboratorio pelo mesmo motivo do anterior;
  
- **Herança**:

  - **Motivação**: Era necessaria a criação de uma Super Classe para representar todos os usuário do laboratorio que não podiam coordenar um projeto e uma sub-classe de usuários que pudessem coordenar projetos.
  - **Solução**: Foram criadas então a Super Classe Usuário, que contem todas as informações sobre um usuário do laboratório, e a sub-classe Coordenador, que representa aqueles usuários que podem coordenar projetos, no caso professores e pesquisadores.
  - **Vantagens**: Caso a herança não fossem ultilizada, seria necessario por o atributo "Projetos Coordenados" na classe Usuário, porém, caso o usuário não fosse professor ou pesquisador, este ArrayList estaria sempre vazio, sendo assim inútil para muitos usuário,
  por isso foi criada esta sub-classe.
  - **Desvantagens**: Por aumentar a quantidade de classes, deixa o programa mais extenso, assim podendo ficar confuso na hora de fazer manuntenção ou quando surgir possiveis bugs.
  
- **Tratamento de Exceções**:

  - **Motivação**: Era necessária a criação de um mecanismo que tornasse a mensagem de erro algo mais amigável e compreensivel aos olhos dos usuário.
  - **Solução**: Foi então criado o método LerInteiro(), que em sua composição tem um try e um catch, que captura erros de tipo diferente na entrada, por exemplo quando o sistema espera um inteiro e o usuário entra uma string, 
  assim enviando uma mensagem compreensivel ao usuário quando este tipo de situação ocorrer, não a mensagem enorme de erro que assusta o usuário. O programa também filtra duplicatas, sejam usuários com nomes iguais, projetos, etc. Sempre enviando uma mensagem compreensivel quando algo ocorrer.
  - **Vantagens**: O tratamento de erro é algo totalmente necessário para que o usuário entenda o que esta acontecendo de errado, assim propiciando que ele consiga usar o sistema.
  - **Desvantagens**: Varias linhas de códigos são empregadas no tratamento de exceções, assim tornando o código muito mais extenso, podendo atrapalhar em uma possivel manuntenção, tornando o código cansativo de ser análisado por completo, porém as vantagens são muito maiores que as desvantagens.
  
- **Extensibilidade**: 
  
  - **Motivação**: É possivel que no futúro, diferentes tipos de colaboradores sejam aceitos no laboratório, além dos ja especificados inícialmente, portanto, o sistema deve permitir que novas sub-classes sejam criadas do super classe Usuario.
  - **Solução**: Os métodos e atributos da Classes Projeto, Atividade e Laboratório foram feitos ultilizando a Super Classe Usuario, como por exemplo o HashMap que armazena os participantes de um projeto, ele armazena o tipo Usuário, assim permitindo que mesmo que uma nova sub-classe seja craida,
  não sera necessário a alteração deste HashMap, assim como todos os outros atributos e metodos, permitindo assim q seja totalmente viável a criação de novas sub-classes.
  - **Vantagens**: É muito bom que o programa contega extensibilidade, pois caso contrario, a criação de uma nova sub-classe pode acarretar a mudanças enormes no sistema, assim se tornando algo pouco viável e trabalhoso.
  - **Desvantagens**: Não vejo desvantagens no uso da extensibilidade.

- **Reuso**:
  
  - **Motivação**: Algumas linhas de código muitas vezes podem se repetir, deixando o código muito mais extenso que o necessário.
  - **Solução**: Foi criado então o metodo LerInteiro(), que contém um trecho de código que era repetido várias e várias vezes no programa, pois faz parte do tratamento de exceções e atua na leitura de inteiros,
  assim reduzindo o número de linhas do código e tornando ele mais eficiente.
  - **Vantagens**: O reuso de metodos permite que não seja necessária a repetição de um trecho especifico, assim deixando o código mais eficiente.
  - **Desvantagens**: Não vejo desvantagens no reuso de metodos.  
