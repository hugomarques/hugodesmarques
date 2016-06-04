---
layout: post
title:  "Introdução ao AWS: 10 exemplos de uso"
date:   2016-04-18
categories: aws general
comments: true
---
**Amazon Web Services** ou **AWS** é uma plataforma de computação nas nuvens ou seja, servidores, banco de dados, arquivos e até mesmo processamento de dados são disponibilizados em forma de serviços na internet.

Com essa abstração, o desenvolvedor pode focar no desenvolvimento de aplicações focando nas funcionalidades e delegando para a *Amazon* o gerenciamento de toda a infraestrutura.

## Diferentes casos de uso

O objetivo desse artigo é demonstrar os diferentes funcionalides que podem ser implementadas utilizando os serviços do *AWS*.

Não irei me aprofundar no uso das APIs ou configuração dos serviços. Isso será um tema para próximos posts.

### 1. Consultas e transações

{% include image.html url="/assets/2016/04/aws/Database_AmazonRDS.png" description="RDS"  %}

**Amazon RDS** permite a criação de diversos banco de dados, entre eles *Oracle* e *MySQL* garantindo transações *ACID* e *queries* em *SQL*.

### 2. Banco de dados escalável e de baixa latência

{% include image.html url="/assets/2016/04/aws/Database_AmazonDynamoDB.png" description="DynamoDB"  %}

**Amazon DynamoDB** é um banco de dados *NoSQL* que pode armazenar dados tanto no modelo chave-valor, como documentos utilizando *JSON*.

### 3. Servidor próprio

{% include image.html url="/assets/2016/04/aws/Compute_AmazonEC2.png" description="EC2"  %}

Um dos serviços principais do Amazon Web Services. O **Amazon EC2** permite ao desenvolvedor configurar máquinas virtuais Linux ou Windows.

Essas máquinas podem ser utilizadas como servidores para rodar desde banco de dados até aplicações complexas como Apache Hadoop.

### 4. Servidor de aplicação

{% include image.html url="/assets/2016/04/aws/Compute_AWSElasticBeanstalk.png" description="Elastic Beanstalk"  %}

Servidores de aplicação podem ser configurados utilizando o **Amazon EC2**. Porém, o **Amazon Elastic Beanstalk** é uma solução mais simples que abstrai grande partes das configurações do *EC2* e permite o deploy de aplicações com 1 clique.

Com o **Elastic Beanstalk** é possível executar aplicações *Java, PHP, JavaScript, Ruby, Python, .NET* ou até mesmo containers como *Docker*.

### 5. Armazenamento de dados

{% include image.html url="/assets/2016/04/aws/Storage-Content-Delivery_AmazonS3.png" description="Amazon S3"  %}

**Amazon S3** é o serviço apropriado para salvar arquivos como imagens, vídeos, músicas ou grandes arquivos de texto.


### 6. Processamento de messagens assíncronas

{% include image.html url="/assets/2016/04/aws/Application-Services_AmazonSQS_message.png" description="Amazon SQS"  %}

Um dos meus serviçoes favoritos, o **Amazon SQS** permite o envio de messagens para processamento assíncrono. O uso de filas de messagens permite a criação de aplicações altamente escaláveis que desacoplam produtor do consumidor.

### 7. Push de messagens no modelo Publisher-Subscriber

{% include image.html url="/assets/2016/04/aws/Mobile-Services_AmazonSNS.png" description="Amazon SNS"  %}

O **Amazon SNS** implementa o *pattern* de **integração** *publisher-subscriber*. Através do **SNS** é possível enviar notificações para diversos canais diferentes, como email, SMS, notifições iOS, Android.

### 8. Execução de workflows

{% include image.html url="/assets/2016/04/aws/Application-Services_AmazonSWF.png" description="Amazon SWF"  %}

O **Amazon SWF** execução de workflows com retentativas, monitoramento de cada passo e lógica de negócio complexas.

### 9. Executar fluxos de dados

{% include image.html url="/assets/2016/04/aws/Analytics_AWSDataPipeline.png" description="Amazon DataPipeline"  %}

Se o objetivo for simplesmente mover dados entre recursos do *AWS* sem necessidade de muita codificação o **Amazon Data Pipeline** é o serviço correto.

Com o DataPipeline é possível mover dados entre *buckets S3*, tabelas do *DynamoDB* ou mesmo realizar *Map-Reduce* através de atividades *Hadoop* ou *Hive*.

### 10. Monitoramento de recursos.

{% include image.html url="/assets/2016/04/aws/Management-Tools_AmazonCloudWatch.png" description="Amazon CloudWatch"  %}

Para monitoramento de todos os recursos descritos acima o *AWS* disponibiliza o **Amazon CloudWatch** que permite acompanhar o desempenho de todos os serviços, além de fornecer métricas e configuração de alarmes.

## Conclusão

O **AWS** é um gigante possuindo mais de 30 serviços disponíveis. Devido a tal tamanho, não consegui mencionar todos os serviços disponíveis como ,por exemplos, **AWS Lambda** que permite a criação de aplicações reativas a eventos.

É extremamente interessante conhecer as ferramentas existentes e como elas resolvem diferentes problemas, isso incrementa o *array* de opções disponíveis ao desenvolvedor podendo economizar tempo na resolução de um problema futuro.

Caso vocês tenham alguma curiosidade com relação ao *AWS* não deixem de postar um comentário, isso pode me ajudar a entender onde focar os próximos posts.

## Referências
* [Amazon Web Services - AWS](http://aws.amazon.com/)
* [Amazon RDS](https://aws.amazon.com/rds/)
* [Amazon DynamoDB](https://aws.amazon.com/dynamodb/)
* [Amazon EC2](https://aws.amazon.com/ec2/)
* [Amazon ElasticBeanstalk](https://aws.amazon.com/elasticbeanstalk/)
* [Amazon S3](https://aws.amazon.com/s3/)
* [Amazon SQS](https://aws.amazon.com/sqs/)
* [Amazon SNS](https://aws.amazon.com/sns/)
* [Amazon SWF](https://aws.amazon.com/swf/)
* [Amazon Data Pipeline](http://aws.amazon.com/documentation/data-pipeline/)
* [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/)
