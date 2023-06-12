---
title: Uma Pouco Sobre API Gateway
author: gsdesenvolvedor
date: 2023-03-19 01:01:00 +0300
categories: [APIs]
tags: [api-gateway, api, apis]
render_with_liquid: false
---

## Insight

Certo dia rotineiro de programação séria* desenvolvendo um API Backend (ou uma API Server), não consigo parar de pensar que em determinado momento terei que desenvolver autenticação e autorização para todas essas APIs serem consumidas pelos #frontenders.

Deste ponto surgem as dúvidas de dev... Crio autenticação e autorização em todas e conecto todas a um banco de dados separado para autenticação? Crio uma API só para autenticação? Que tipo de monstro eu estou criando hoje? Tenho vitalidade o suficiente para pagar essa dívida técnica mais tarde?

Eu já tinha ouvido falar sobre API Gateway em um momento remoto da minha jornada, mas não coletei essa informação e acabei abstraindo e então diante do problema apresentado acima, eu fui pesquisar alternativas para quando se tem vários backends e vários frontends que precisam se conversar através de API, utilizando autenticação e autorização.

E é claro! API Gateway, tão óbvio... Então, se você estiver passando pela mesmo situação, vou falar um pouco mais sobre essa iguaria nesta publicação.

## O que é API Gateway?

API Gateway é uma solução de software que atua como um ponto de entrada para uma ou várias APIs, permitindo gerenciá-las de forma centralizada. Basicamente, é uma camada intermediária que fica entre as aplicações clientes (como websites, aplicativos mobile ou outros sistemas) e as APIs que fornecem os dados ou serviços que eles necessitam.

A API Gateway é responsável por receber as requisições dos clientes, encaminhá-las para a API apropriada e retornar as respostas correspondentes. Além disso, ela também oferece uma série de recursos adicionais, como autenticação, autorização, segurança, monitoramento e transformação de dados.

### Algumas das principais funcionalidades de uma API Gateway incluem:

- Roteamento: a API Gateway é responsável por receber as requisições dos clientes e encaminhá-las para a API correta.
- Autenticação e autorização: a API Gateway pode verificar a autenticidade das requisições e garantir que apenas os usuários autorizados tenham acesso aos dados ou serviços disponibilizados pelas APIs.
- Transformação de dados: a API Gateway pode manipular os dados enviados pelos clientes ou retornados pelas APIs, convertendo-os para diferentes formatos ou fazendo ajustes para melhorar a compatibilidade entre as diferentes partes da aplicação.
- Segurança: a API Gateway pode proteger as APIs contra ataques maliciosos, como ataques de negação de serviço (DDoS) ou tentativas de invasão.
-Monitoramento: a API Gateway pode coletar e analisar métricas de desempenho e uso das APIs, permitindo que os desenvolvedores identifiquem problemas e façam ajustes para melhorar a eficiência e a escalabilidade da aplicação.

As API Gateways são amplamente utilizadas em arquiteturas de microserviços, pois permitem que as APIs sejam escalonadas de forma independente e gerenciadas de forma mais eficiente. Além disso, elas também permitem que as APIs sejam expostas de forma pública ou privada, dependendo das necessidades do negócio.

![API Gateway Pattern](https://raw.githubusercontent.com/codigoeconteudo/cdn/main/blog/posts/api-gateway-pattern.png)

## Algumas das principais vantagens do uso de uma API Gateway são:

- Simplificação da arquitetura de APIs: o uso de uma API Gateway permite que as APIs sejam gerenciadas de forma centralizada, simplificando a arquitetura geral da aplicação.
- Escalonamento independente: com a API Gateway, é possível escalonar cada API de forma independente, o que pode melhorar a eficiência e a escalabilidade da aplicação.
- Gerenciamento de segurança: a API Gateway pode oferecer recursos de autenticação, autorização e segurança, o que ajuda a proteger as APIs contra ataques maliciosos.
- Monitoramento centralizado: a API Gateway permite que as métricas de desempenho e de uso das APIs sejam monitoradas de forma centralizada, facilitando a identificação de problemas e a tomada de decisões.
- Implementação de políticas de governança: a API Gateway permite que as organizações implementem políticas de governança, como limites de taxa, quotas de uso e gerenciamento de versões de API, para garantir o uso adequado das APIs.
- Integração com diferentes sistemas e tecnologias: a API Gateway pode integrar diferentes sistemas e tecnologias, permitindo que as APIs se comuniquem com outras aplicações e serviços, independentemente das tecnologias utilizadas por eles.
- Facilidade de uso para os desenvolvedores: a API Gateway oferece uma interface simples e padronizada para os desenvolvedores utilizarem as APIs, o que torna mais fácil para eles consumirem as APIs e acelerar o desenvolvimento de novas funcionalidades.
- Flexibilidade na escolha de tecnologias: a API Gateway permite que as organizações escolham as tecnologias mais adequadas para cada componente da solução, o que pode resultar em uma arquitetura mais flexível e adaptável às necessidades do negócio.

## Algumas das desvantagens de uma API Gateway incluem:

- Complexidade de implementação: a construção e manutenção de uma API Gateway pode ser complexa, exigindo um conhecimento avançado em arquitetura de sistemas distribuídos e desenvolvimento de software.
- Latência adicional: a API Gateway adiciona uma camada adicional de processamento e comunicação na arquitetura da aplicação, o que pode aumentar a latência das requisições.
- Custo: o uso de uma API Gateway pode gerar custos adicionais para a organização, tanto em termos de desenvolvimento e manutenção quanto em relação às soluções de API Gateway disponíveis no mercado.

## Principais ferramentas disponíveis no mercado

- Amazon API Gateway: serviço da Amazon Web Services (AWS) para gerenciamento de APIs.
- Apigee Edge: plataforma de gerenciamento de APIs da Google Cloud.
- Kong: plataforma de gerenciamento de APIs de código aberto.
- Azure API Management: serviço de gerenciamento de APIs da Microsoft Azure.

## Consigo desenvolver minha própria API Gateway?

Sim, é possível, embora seja um processo complexo e que exige um conhecimento avançado em arquitetura de sistemas distribuídos e desenvolvimento de software.

Para desenvolver sua própria API Gateway, é necessário considerar diversos fatores, tais como segurança, escalabilidade, desempenho e monitoramento. Além disso, é preciso escolher as tecnologias adequadas para cada um dos componentes da solução, como o servidor web, o banco de dados, a plataforma de mensageria, entre outros.

Algumas das tecnologias mais utilizadas para desenvolvimento de API Gateways incluem:

- Servidor web: Nginx, Apache, Express.js, entre outros.
- Banco de dados: MongoDB, PostgreSQL, MySQL, entre outros.
- Plataforma de mensageria: RabbitMQ, Kafka, Redis, entre outros.

É importante destacar que o desenvolvimento de uma API Gateway envolve um grande esforço de desenvolvimento e manutenção, especialmente em relação à segurança. Portanto, muitas empresas optam por usar soluções de API Gateway existentes, como o Amazon API Gateway, Apigee Edge, Kong e Azure API Management, que já oferecem recursos prontos para uso e são mantidas por equipes dedicadas.

No geral, a API Gateway é uma solução útil para simplificar o gerenciamento e a exposição de APIs em arquiteturas de microserviços, permitindo que as organizações ofereçam seus serviços de forma mais eficiente e segura. No entanto, é importante avaliar cuidadosamente as necessidades da organização antes de optar por desenvolver ou adquirir uma API Gateway.

## Referências

Amazon API Gateway. Disponível em: https://aws.amazon.com/pt/api-gateway/.
Apigee Edge. Disponível em: https://cloud.google.com/apigee.
Kong. Disponível em: https://konghq.com/.
Azure API Management. Disponível em: https://azure.microsoft.com/pt-br/services/api-management/.