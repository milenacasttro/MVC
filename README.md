# Design de Arquitetura

![exemplo_arq.jpg](https://github.com/kterra/Inteli-2024-1B/blob/main/materiais/ponderada-2/exemplo-arq-v2.jpg)

Link do diagrama no Draw.io: (https://drive.google.com/file/d/1OwpdrphHBkzYyqSsLqxjPUiNQrL5-BEv/view?usp=sharing) 

# Arquitetura MVC
- Nome do Projeto: TechBridge
- Descrição: Web site para apoiar os jogadores do Cesim Global Challenge a compreender as diferenças culturais existentes entre eles e melhorar a comunicação entre eles, por meio do preenchimento de questionários e a visualização intuitiva dos dados coletados.

- Arquitetura: MVC (Model-View-Controller)
- Ferramenta de Diagramação: Draw.io

### Modelos (Models):
User Player: modelo que representa os usuários do site que são jogadores do Cesim. Sendo que ele armazena os seguintes atributos:

- id: Identificador único do usuário;
- nome: Nome do usuário;
- pais: País de origem do jogador;
- id_time: Identificador único do time que o jogador pertence;
- email: Endereço de e-mail do usuário;
- senha: Senha do usuário.

User Tutor: modelo que representa os usuários do site que são tutores do Cesim. Sendo que ele armazena os seguintes atributos:

- id: Identificador único do usuário;
- nome: Nome do usuário;
- pais: País de origem do tutor;
- ids_times: Identificadores únicos dos times do tutor;
- email: Endereço de e-mail do usuário;
- senha: Senha do usuário.

Perfil: modelo que armazena o perfil de liderança do jogador, obtido por meio de um questionário. Sendo que ele possui os seguintes atributos:

- perfil_de_lideranca: Tipo de perfil de liderança do usuário;
- respostas_questionario: Respostas do usuário ao questionário de perfil.

Nível de felicidade: modelo que armazena os dados do nível de felicidade do jogador e do seu grupo. Sendo que ele possui os seguintes atributos:

- porcentagem_individual: Porcentagem individual de felicidade do usuário;
- porcentagens_grupo: Porcentagens de felicidade do grupo do usuário.

Relações entre Entidades:
- Um User Player pertence a um único time (id_time);
- Um User Tutor pode estar associado a vários times (ids_times);
- O Perfil está relacionado diretamente com um usuário, seja Player ou Tutor;
- O Nível de Felicidade está relacionado com um usuário e seu grupo.


### Controladores (Controllers):
User Player:
- Listar: Retorna a lista de todos os jogadores;
- Gravar: Salva um novo jogador no sistema;
- Procurar: Busca por um jogador específico.

User Tutor:
- Listar: Retorna a lista de todos os tutores;
- Gravar: Salva um novo tutor no sistema;
- Procurar: Busca por um tutor específico.

Perfil:
- Gravar: Salva as respostas do questionário de perfil de liderança;
- Visualizar: Retorna o perfil de liderança de um usuário específico.

Nível de Felicidade:
- Gravar: Salva os dados de felicidade do usuário e seu grupo;
- Visualizar: Retorna os dados de felicidade do usuário e seu grupo;
- Calcular: Calcula a porcentagem de felicidade do usuário e do grupo.

Interação com Modelos e Views:
- Os controladores interagem com os modelos para acessar e manipular os dados do banco de dados. Eles também interagem com as views para fornecer dados para serem exibidos aos usuários ou receber dados inseridos pelos usuários.


### Views (Views):
Tela de Login: 
- Formulário que possibilita acessar o site por meio do preenchimento do email e da senha já cadastrados.

Questionário de perfil: 
- Formulário que apresenta uma pergunta e duas alternativas por vez e traça o perfil de liderança do usuário.

Medidor de felicidade: 
- Formulário que apresenta três alternativas de nível de felicidade e expõe uma felicidade média do grupo.

### Infraestrutura:
- Banco de Dados PostgreSQL: Utiliza-se o PostgreSQL como banco de dados para armazenar os dados do site;
- Render: Utiliza-se o Render para hospedar o aplicativo web, garantindo alta disponibilidade e desempenho;
- DBeaver: Utiliza-se o DBeaver para gerenciar e visualizar os dados armazenados no banco de dados PostgreSQL.
  
Integração com MVC:
- Banco de Dados PostgreSQL: O PostgreSQL será integrado à arquitetura MVC como o componente de modelo (Model). As tabelas do banco de dados serão mapeadas para modelos na aplicação. Os controladores (Controllers) interagirão com esses modelos para acessar e manipular os dados, mantendo a lógica de negócios separada da camada de visualização (View).
  
- Render: A plataforma Render será responsável por hospedar a aplicação web, incluindo os controladores, modelos e visualizações.
  
- DBeaver: O DBeaver será utilizado como uma ferramenta de administração e gerenciamento do banco de dados PostgreSQL. Ele não está diretamente integrado à arquitetura MVC, mas será usado para auxiliar no desenvolvimento, depuração e manutenção do banco de dados.


### Justifique as escolhas feitas e como elas impactam o projeto.
#### Implicações da Arquitetura:
Essa integração entre os componentes de infraestrutura e a arquitetura MVC garantirá uma aplicação web escalável, segura e de alto desempenho.


