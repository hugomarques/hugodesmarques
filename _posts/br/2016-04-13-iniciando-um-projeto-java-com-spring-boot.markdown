---
layout: post
title:  "Java fácil com Spring Boot"
date:   2016-04-13
categories: java spring
comments: true
---

Iniciar um novo projeto *Java* é uma tarefa chata e complicada pois múltiplas dependências e configurações são necessárias antes de ter um simples *Hello World* rodando em um *server* local.

**Spring Boot** é um projeto do *[Spring](spring) framework* que simplifica todo o processo de criar uma nova aplicação.

Utilizando **Spring Boot** é possível criar uma aplicação em menos de 5 minutos com todo o suporte do **Spring framework** como *Injeção de dependências* e *AOP*, além de dependências adicionais como *logging, unit testing, databases*, entre outros.

O exemplo completo desse post está disponível no **[github](https://github.com/hugomarques/PoCExamples/tree/master/demo)**.

## Iniciando um projeto

#### 1. Crie um novo projeto

Acesse o link: https://start.spring.io/

![spring-boot-web-01](/assets/2016/04/spring-boot-initializr-01.png)

Usuário do IntelliJ, podem fazer esse processo na própria *IDE*.

![spring-boot-01](/assets/2016/04/spring-boot-01.png)

#### 2. Escolha que tipo de projeto você deseja criar

![spring-boot-web-02](/assets/2016/04/spring-boot-initializr-02.png)

Clique em generate e faça download do pacote gerado.

#### 3. Importe o pacote em sua IDE de preferência como um projeto Maven

O projeto gerado segue a estrutura padrão do *Maven*

![spring-boot-04](/assets/2016/04/spring-boot-04.png)

Todas as dependências podem ser verificadas no arquivo *pom.xml*

{% gist hugomarques/c2c2ab12c7bc1683bd371ddcd0fbae24 pom.xml %}

#### 4. Execute o projeto

Execute a classe *DemoApplication.java* e observe o código executando no console.

{% gist hugomarques/c2c2ab12c7bc1683bd371ddcd0fbae24 DemoApplication.java %}

#### 5. Adicione um controller

Adicione um novo componente *Spring* que funciona como um *controller Rest*, o objetivo é retornar a *String Hello World* da aplicação.

{% gist hugomarques/c2c2ab12c7bc1683bd371ddcd0fbae24 HelloWorldController.java %}

Execute a classe *DemoApplication.java* novamente, acesse **http://localhost:8080/** no seu browser e verifique que **Hello World** foi impresso com sucesso.

#### 6. Teste seu contexto Spring

Acesse a classe *DemoApplicationTests.java* e a altere para verificar se o contexto *Spring* está acessando seus componentes corretamente:

{% gist hugomarques/c2c2ab12c7bc1683bd371ddcd0fbae24 DemoApplicationTests.java %}

Execute o código acima como um teste *JUnit* e verifique que o teste é executado com sucesso.

## Próximos passos

Com o projeto criado e executando podemos continuar implementando novas funcionalidades incrementalmente. É importante destacar que todo o *bootstrap* feito pelo *Spring Boot* pode ser configurado manualmente utilizando as tecnologias *Spring* padrões como o [Spring Core][spring-core] e o [Spring Web][spring-web].

Em próximos posts, irei explorar diversas funcionalidades disponíveis no *Spring Boot* e em outros projetos do *Spring framework* que visam facilitar o desenvolvimento de aplicações.


[spring-framework]: https://spring.io/
[spring-boot]: http://projects.spring.io/spring-boot/
[spring-core]: http://docs.spring.io/spring/docs/4.3.0.RC1/spring-framework-reference/htmlsingle/#overview-core-container
[spring-web]: http://docs.spring.io/spring/docs/4.3.0.RC1/spring-framework-reference/htmlsingle/#overview-web
