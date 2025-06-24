# Instruções para desenvolvimento do teste Full-stack LinkLei.

- O prazo de entrega do teste é de até 7 dias, a partir do momento que acordarmos o início do desenvolvimento mediante contato.
- O mais importante é desenvolver todos os requisitos listados aqui. Você também pode desenvolver funcionalidades adicionais para agregar valor ao seu teste.


## Requisitos Gerais:

- Leia todo este arquivo README.md para entender o teste;
- Inicie um novo repositório público em sua conta no github;
- Para o back-end utilize:
  - [PHP 8.2+](http://php.net/);
  - [MySQL 8+](https://www.mysql.com/);
  - Framework [Laravel](https://laravel.com/), [versão 8](https://laravel.com/docs/8.x);
- Para o front-end utilize:
  - [React JS 17](https://pt-br.reactjs.org/) ou mais recente;
- Você pode desenvolver o front-end integrado ao Laravel, através dos seguintes recursos:
  - [Compilação JS do Laravel](https://laravel.com/docs/8.x/mix#react) (recomendado)
  - OU
  - criando uma nova aplicação react somente para o front [aqui](https://react.dev/learn/creating-a-react-app).
  - Lembre apenas de manter as duas aplicações no mesmo repositório para facilitar análise do teste;
- Realize as comunicações entre Front e Back desenvolvendo uma API JSON minimalista em Laravel;
- Não há necessidade de desenvolver recursos de Autenticação, Login, ou quaisquer sistemas de segurança;
- **O objetivo principal é desenvolver um feed simples de rede social;**
- Busque criar um código bem estruturado, seguindo um padrão e as melhores práticas da comunidade. Sinta-se livre para acrescentar comentários, lembretes e anotações diversas no código.
- Consideramos positivo um código bem comentado;
- Em um ambiente de desenvolvimento corporativo é fundamental que a equipe compreenda todos os códigos desenvolvidos;
- Após finalizar, publique no repositório do seu projeto um arquivo completo com o SQL do seu banco utilizado (dump do banco);
- Não é necessário publicar o projeto em algum servidor.
- Insira no seu `README.md` todas as instruções ou documentações necessárias para executarmos localmente seu projeto para avaliação;
  - Lembre de incluir quaisquer instruções necessárias para a execução do ambiente, como versões das dependências, em especial do PHP, Lavarel, Node, React e MySQL.
  - Detalhe também as versões de pacotes externos utilizados em node.
- Utilize como base de design o mockup nas imagens abaixo.
- Ao finalizar o teste responda à mesma conversa de email onde enviamos o link do desafio. Inclua na sua resposta o link do seu repositório no github.
- Utilize sua criatividade e experiência no desenvolvimento de um designe bonito, elegante e principalmente funcional;
- Lembre de criar um layout **responsivo**, proporcionando uma boa experiência para os usuários em diferentes dispositivos mobile, smartphones, tablets e desktops;
- **Valorizamos a aplicação de boas práticas em UX;**
- Considere utilizar bibliotecas de ícones e componentes npm para demonstrar sua experiência e maximizar os recursos de desenvolvimento;
- Utilize o padrão de fonte 'Lato', como no exemplo abaixo:
```css
font-family: Lato,'Source Sans Pro';
```

## A aplicação:
- Desenvolva uma aplicação simples de feed de publicações, similar ao feed de uma rede social (facebook, linkedin...);

## Requisitos funcionais da aplicação:

### Criar post
- O botão **Criar Post** deve abrir a modal para cadastro de post.
- Mockup referêncial:
![Modal Criar Post](https://github.com/linklei-dev/frontend-test-laravel-react/blob/main/graphics/mockup_modal_create.png?raw=true)

### Dentro da Modal:
  - campo **autor do post**: preenchimento obrigatório, campo tipo texto, deve receber o nome do usuário que está publicando.
  - campo **Selecione a categoria**: obrigatório, deve ser do tipo select, permitindo selecionar uma das categorias disponíveis, sendo elas:
    - Post
    - Artigo
    - Grupo
  - Campo **Escrever publicação**: obrigatório, deve ser do tipo texto com elmentos pra formatação, permitindo multiplas linhas de texto. Utilize um componente que faça o campo crescer verticalmente quando acrescentadas mais linhas de texto. Recomendamos componentes como QuillJS, TinyMCE, DraftJS... 
  - Permitir inserir imagens na publicação. Deve aceitar somente imagens no formato jpg ou png;
  - Botão **publicar** envia todo o conteúdo da criação do post para a API, salvando a categoria e texto na respectiva tabela do post;
  - Caso existam imagens no campo texto, elas devem ser enviadas para a aplicação e salvas em um diretório local;
  - Após enviar o conteúdo do post, a modal deve ser fechada automaticamente.
  - Realize as validações necessárias, exibindo mensagens de erro quando algum campo não estiver preenchido ou for inválido. Use sua sabedoria para decidir como, onde e quando exibir estas mensagens de erro/validações.
  - Não há necessidade e validar o tamanho da imagem quando enviada.

  ### Navegação no feed.
  - Mockup referencial do feed:
  ![template_feed](https://github.com/linklei-dev/frontend-test-laravel-react/blob/main/graphics/mockup_feed.png?raw=true)

  - O feed deve exibir todos os posts criados, em ordem Decrescente (primeiro o post mais recente).
  - A imagem do usuário deve ser o [avatar_default](https://github.com/linklei-dev/fullstack-test-laravel/blob/main/graphics/avatar_default.png?raw=true);
  - Limite a exibição do texto do post para no máximo 500 caracteres, caso exceda este limite, exiba o link "Leia mais..." que ao ser clicado deve expandir a caixa e exibir por inteiro o texto do post. Caso o limite não seja excedido, não exibir o "Leia mais...".
  - Utilize recursos de rolagem infinita, para carregar mais posts quando a rolagem do usuário chegar no fim da página.
  - Siga as boas práticas de desenvolvimento React, procure utilizar componentes disponíveis em comunidades open source (como npm), repositórios no github, etc.
  - Cria recursos para **Deletar** e **Editar** o post.
  - Estas funções devem estar em um menu suspenço (estilo dropdown), no canto superior direito do post no feed, como um botão, seguindo o modelo na imagem abaixo.
    - Editar: exiba o conteúdo do post na mesma modal utilizada na ação de Criar;
    - Deletar: solicite uma confirmação de deleção ao usuário antes de remover o post;
  - Caso o post tenha mais de uma imagem, no modo reduzido (sem ter clicado em ler mais) deve ser exibido apenas a primeira imagem encontrada no texto do post como imagem em destaque.

### Framework React Bootstrap:
- Utilize o framework front-end [React Bootstrap](https://react-bootstrap.github.io/);
- Requisito obrigatório para avaliação de suas habilidades ao utilizar um robusto framework de componentes front-end;

## Diferenciais:
Recursos adicionais **não obrigatórios** que podem agregar valor ao seu teste.
- Criar um ambiente em docker para executar a aplicação e o banco de dados;
- Melhores práticas e uso dos padrões de código aceitos pela comunidade Laravel/PHP/React;
- Seja criativo! Recursos adicionais como melhorias no design, novos componentes ou ferramentas também agregam ao seu teste.

-----------------

**Bom trabalho ;)**

-----------------

