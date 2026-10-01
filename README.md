agendaPHP

Sistema de Agenda Eletrônica desenvolvido em PHP, com banco de dados MySQL e interface baseada no AdminLTE.
Sobre o projeto

O agendaPHP é um sistema web para gerenciamento de contatos. O sistema permite que usuários realizem cadastro e login para acessar uma agenda eletrônica, onde podem cadastrar, visualizar, editar e excluir contatos.

Cada contato pode possuir nome, telefone, e-mail e foto.

O sistema também possui gerenciamento do perfil do usuário, relatório de contatos e recursos para geração de documentos em PDF.
Funcionalidades

    Cadastro de usuários
    Login e autenticação por sessão
    Senhas armazenadas utilizando hash
    Cadastro de contatos
    Listagem de contatos
    Edição de contatos
    Exclusão de contatos
    Upload de fotos de usuários
    Upload de fotos dos contatos
    Avatar padrão para usuários e contatos
    Visualização do perfil
    Alteração de informações do perfil
    Relatório com todos os contatos
    Pesquisa e organização da lista de contatos
    Geração de PDF
    Sistema protegido por sessão
    Associação dos contatos ao usuário cadastrado

Tecnologias utilizadas

    PHP
    MySQL
    PDO
    HTML5
    CSS3
    JavaScript
    AdminLTE
    Bootstrap
    Font Awesome
    DataTables
    SweetAlert2
    Toastr
    Select2
    Summernote
    Dompdf

Estrutura do projeto

agendaPHP/
│
├── config/
│   └── conexao.php
│
├── dist/
│   ├── css/
│   ├── img/
│   └── js/
│
├── img/
│   ├── avatar_p/
│   ├── cont/
│   ├── logo/
│   └── user/
│
├── includes/
│   ├── footer.php
│   ├── header.php
│   └── sair.php
│
├── paginas/
│   ├── home.php
│   └── conteudo/
│       ├── cadastro_contato.php
│       ├── del-rel-contato.php
│       ├── perfil.php
│       ├── relatorio.php
│       ├── update_contato.php
│       └── pdf/
│
├── plugins/
│
├── cad_user.php
├── index.php
├── new_agenda.sql
└── README.md

Banco de dados

O projeto utiliza o banco de dados:

new_agenda

O arquivo new_agenda.sql contém a estrutura necessária para criar o banco de dados.

As principais tabelas são:
tb_user

Armazena os usuários do sistema.

Principais campos:

    id_user
    foto_user
    nome_user
    email_user
    senha_user

tb_contatos

Armazena os contatos cadastrados na agenda.

Principais campos:

    id_contatos
    nome_contatos
    fone_contatos
    email_contatos
    foto_contatos
    id_user

Os contatos possuem uma relação com o usuário por meio do campo id_user.
Configuração do banco de dados

A conexão com o banco é realizada no arquivo:

config/conexao.php

A configuração utilizada pelo projeto é:

Host: localhost
Banco: new_agenda
Usuário: admin

A aplicação utiliza PDO para realizar a conexão e executar as consultas no banco de dados.
Como executar o projeto
1. Instale os requisitos

É necessário ter instalado:

    PHP
    MySQL
    Apache ou outro servidor compatível com PHP
    Extensão PDO para MySQL

2. Configure o banco de dados

Crie o banco de dados new_agenda no MySQL.

Depois, importe o arquivo:

new_agenda.sql

Esse arquivo cria as tabelas e relacionamentos utilizados pelo sistema.
3. Configure a conexão

Abra:

config/conexao.php

Confira os dados de acesso ao MySQL e altere-os caso sejam diferentes no seu ambiente.
4. Execute o projeto

Coloque a pasta agendaPHP no diretório do servidor web.

Por exemplo, utilizando Apache/XAMPP:

htdocs/
└── agendaPHP/

Depois, inicie o Apache e o MySQL.

Acesse no navegador:

http://localhost/agendaPHP/

Fluxo do sistema

O funcionamento básico do sistema é:

Página inicial
      ↓
Login
      ↓
Autenticação
      ↓
Agenda Eletrônica
      ↓
Cadastro de contatos
      ↓
Visualização dos contatos
      ↓
Edição ou exclusão

O acesso às páginas internas depende da autenticação do usuário.
Cadastro de usuário

O cadastro é realizado através do arquivo:

cad_user.php

O usuário pode informar:

    Nome
    E-mail
    Senha
    Foto

A senha é armazenada utilizando password_hash().
Login

O login é realizado através do arquivo:

index.php

O sistema verifica o e-mail cadastrado e utiliza password_verify() para conferir a senha.

Após o login, são criadas variáveis de sessão para controlar o acesso ao sistema.
Gerenciamento de contatos

A página principal da agenda permite cadastrar novos contatos.

Para cada contato podem ser informados:

    Nome
    Telefone
    E-mail
    Foto

Os contatos são armazenados no banco de dados e relacionados ao usuário responsável pelo cadastro.
Edição de contatos

A edição é realizada através de:

paginas/conteudo/update_contato.php

É possível alterar os dados do contato e substituir sua foto.

Quando uma nova foto é enviada, o sistema permite substituir a imagem anterior.
Relatório

O relatório está disponível em:

paginas/conteudo/relatorio.php

Ele apresenta os contatos cadastrados com:

    Foto
    Nome
    Telefone
    E-mail
    Ações de edição
    Ações de exclusão

PDF

O projeto possui integração com a biblioteca Dompdf para trabalhar com geração de documentos PDF.

A configuração do Dompdf está localizada em:

paginas/conteudo/pdf/

Interface

A interface utiliza o AdminLTE como base visual.

Também são utilizados recursos como:

    Bootstrap
    Font Awesome
    DataTables
    Select2
    SweetAlert2
    Toastr
    Summernote
    Tempus Dominus

Essas bibliotecas estão organizadas principalmente dentro da pasta:

plugins/

Segurança

O projeto utiliza alguns recursos para proteção e tratamento dos dados, como:

    Sessões PHP para controle de acesso
    password_hash() para armazenamento das senhas
    password_verify() para autenticação
    PDO para comunicação com o banco
    Consultas preparadas com parâmetros
    Verificação de sessão nas páginas internas
    Validação de extensões de imagens enviadas

Autores

Maryanna Ramos de Oliveira Mary Cecilia Ramos de Oliveira

Projeto desenvolvido para fins acadêmicos e de aprendizado em desenvolvimento web utilizando PHP, MySQL e tecnologias relacionadas.
