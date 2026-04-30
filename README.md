<div align="center">

# 🌐 TechMarket Gateway Service

### Serviço responsável pelo roteamento, segurança e ponto único de entrada da plataforma TechMarket.

<br/>

[![Java](https://img.shields.io/badge/Java_21-ED8B00?style=for-the-badge\&logo=openjdk\&logoColor=white)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge\&logo=spring-boot\&logoColor=white)](https://spring.io/projects/spring-boot)
[![Spring Cloud Gateway](https://img.shields.io/badge/Spring_Cloud_Gateway-6DB33F?style=for-the-badge\&logo=spring\&logoColor=white)](https://spring.io/projects/spring-cloud-gateway)
[![WebFlux](https://img.shields.io/badge/WebFlux-6DB33F?style=for-the-badge\&logo=spring\&logoColor=white)](https://docs.spring.io/spring-framework/reference/web/webflux.html)
[![Eureka](https://img.shields.io/badge/Eureka-FF6F00?style=for-the-badge\&logo=netflix\&logoColor=white)](https://spring.io/projects/spring-cloud-netflix)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge\&logo=docker\&logoColor=white)](https://www.docker.com/)

</div>

---

## 📋 Índice

* [Sobre o Gateway Service](#-sobre-o-gateway-service)
* [Principais Funcionalidades](#️-principais-funcionalidades)
* [Arquitetura e Papel no Sistema](#-arquitetura-e-papel-no-sistema)
* [Tecnologias Utilizadas](#️-tecnologias-utilizadas)
* [Dependências Relevantes](#-dependências-relevantes)
* [Fluxo de Requisição](#-fluxo-de-requisição)
* [Boas Práticas Aplicadas](#-boas-práticas-aplicadas)
* [Integração com Outros Serviços](#-integração-com-outros-serviços)
* [Repositórios](#-repositórios)
* [Autor](#-autor)

---

## 💡 Sobre o Gateway Service

O **Gateway Service** é o ponto central de entrada da arquitetura do TechMarket. Ele atua como um **API Gateway**, responsável por receber todas as requisições do frontend e direcioná-las para os microsserviços apropriados.

Esse serviço foi projetado com foco em:

* **Centralização de acesso**
* **Escalabilidade**
* **Baixo acoplamento entre serviços**

---

## ⚙️ Principais Funcionalidades

* 🌐 Roteamento de requisições para microsserviços
* 🔄 Balanceamento de carga entre instâncias
* 🔍 Integração com Service Discovery (Eureka)
* ⚡ Processamento reativo com WebFlux

---

## 🧱 Arquitetura e Papel no Sistema

O Gateway Service se posiciona como:

```id="q2d9xv"
Frontend → Gateway Service → Microsserviços
                  ↓
        Roteamento dinâmico (Eureka)
```

### Responsabilidades:

| Responsabilidade | Descrição                     |
| ---------------- | ----------------------------- |
| Entrada única    | Ponto central de acesso       |
| Roteamento       | Direcionamento de requisições |
| Integração       | Descoberta via Eureka         |

---

## 🛠️ Tecnologias Utilizadas

### Backend

* Java 21
* Spring Boot 3.5
* Spring Cloud Gateway
* Spring WebFlux (programação reativa)

### Cloud & Infra

* Spring Cloud Netflix Eureka Client
* Docker

### Observabilidade

* Spring Boot Actuator

---

## 📦 Dependências Relevantes

Principais dependências do projeto:

* `spring-cloud-starter-gateway-server-webflux`
* `spring-cloud-starter-netflix-eureka-client`
* `spring-boot-starter-actuator`

---

## 🔄 Fluxo de Requisição

1. Frontend envia requisição HTTP
2. Gateway intercepta a requisição
4. Serviço de destino é identificado via Eureka
5. Requisição é roteada dinamicamente
6. Resposta retorna ao cliente

---

## 📊 Boas Práticas Aplicadas

* Centralização de autenticação no Gateway
* Arquitetura reativa com WebFlux
* Uso de Service Discovery (Eureka)
* Desacoplamento entre cliente e serviços
* Configuração declarativa de rotas
* Observabilidade com Actuator

---

## 🔗 Integração com Outros Serviços

| Serviço           | Integração                       |
| ----------------- | -------------------------------- |
| Discovery Service | Registro e descoberta via Eureka |
| Identity Service  | Roteamento de requisições        |
| Product Service   | Roteamento de requisições        |
| Order Service     | Roteamento de requisições        |
| Payment Service   | Roteamento de requisições        |
| Frontend          | Ponto único de acesso            |

---

## 📁 Repositórios

O TechMarket é organizado como um **monorepo com submódulos Git**. Cada serviço possui seu próprio repositório:

| Serviço | Descrição | Repositório |
|---------|-----------|-------------|
| 🗂️ **techmarket** | Repositório principal (monorepo + Docker Compose) | [github.com/felipesora/techmarket](https://github.com/felipesora/techmarket) |
| 🔍 **discovery-service** | Eureka Server para service discovery | [github.com/felipesora/techmarket-discovery-service](https://github.com/felipesora/techmarket-discovery-service) |
| 🌐 **gateway-service** | API Gateway com Spring Cloud Gateway | [github.com/felipesora/techmarket-gateway-service](https://github.com/felipesora/techmarket-gateway-service) |
| 🔐 **identity-service** | Autenticação e gerenciamento de usuários (JWT) | [github.com/felipesora/techmarket-identity-service](https://github.com/felipesora/techmarket-identity-service) |
| 📦 **product-service** | Catálogo e gerenciamento de produtos | [github.com/felipesora/techmarket-product-service](https://github.com/felipesora/techmarket-product-service) |
| 🛒 **order-service** | Criação e acompanhamento de pedidos | [github.com/felipesora/techmarket-order-service](https://github.com/felipesora/techmarket-order-service) |
| 💳 **payment-service** | Processamento de pagamentos via mensageria | [github.com/felipesora/techmarket-payment-service](https://github.com/felipesora/techmarket-payment-service) |
| 🖥️ **techmarket-web** | Frontend da plataforma em Angular | [github.com/felipesora/techmarket-web](https://github.com/felipesora/techmarket-web) |

---

## 👨‍💻 Autor

Desenvolvido por **Felipe Sora**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/felipesora)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/felipesora)