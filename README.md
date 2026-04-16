# TaskFlow API

API RESTful desenvolvida com **Spring Boot** para gerenciamento de usuários, pedidos, produtos e categorias, seguindo boas práticas de arquitetura em camadas.

## 📌 Visão Geral

O **TaskFlow API** é um projeto backend que simula um sistema de e-commerce, com foco em:

- Estruturação em camadas (Resource → Service → Repository)
- Modelagem de domínio com JPA
- Tratamento de exceções padronizado
- Boas práticas REST

## 🚀 Tecnologias Utilizadas

- Java 17+
- Spring Boot
- Spring Data JPA
- Hibernate
- Maven
- H2 Database (ambiente de teste)
- PostgreSQL / MySQL (produção - configurável)

## 📂 Estrutura do Projeto

```
src/main/java/com/educandoweb/course

├── config
│   └── TestConfig.java
├── entities
│   ├── enums
│   │   └── OrderStatus.java
│   ├── pk
│   │   └── OrderItemPK.java
│   ├── Category.java
│   ├── Order.java
│   ├── OrderItem.java
│   ├── Payment.java
│   ├── Product.java
│   └── User.java
├── repositories
│   ├── CategoryRepository.java
│   ├── OrderItemRepository.java
│   ├── OrderRepository.java
│   ├── ProductRepository.java
│   └── UserRepository.java
├── resources (controllers)
│   ├── exceptions
│   │   ├── ResourceExceptionHandler.java
│   │   └── StandardError.java
│   ├── CategoryResource.java
│   ├── OrderResource.java
│   ├── ProductResource.java
│   └── UserResource.java
├── services
│   ├── exceptions
│   │   ├── DatabaseException.java
│   │   └── ResourceNotFoundException.java
│   ├── CategoryService.java
│   ├── OrderService.java
│   ├── ProductService.java
│   └── UserService.java
└── CourseApplication.java
```

## 🧠 Arquitetura

- **Resource (Controller)** → Requisições HTTP
- **Service** → Regras de negócio
- **Repository** → Acesso a dados (JPA)
- **Entities** → Modelo de domínio

## 🔗 Endpoints Principais

### Usuários
- GET /users
- GET /users/{id}
- POST /users
- DELETE /users/{id}

### Produtos
- GET /products
- GET /products/{id}

### Categorias
- GET /categories
- GET /categories/{id}

### Pedidos
- GET /orders
- GET /orders/{id}

## ⚙️ Como Executar

### Pré-requisitos
- Java 17+
- Maven

### Passos

```
git clone https://github.com/seu-usuario/taskflow-api.git
cd taskflow-api
./mvnw spring-boot:run
```

Acesse: http://localhost:8080

## 🧪 Ambiente de Teste

- Banco H2 configurado
- Console: http://localhost:8080/h2-console

## ⚠️ Tratamento de Exceções

Exemplo de resposta:

```json
{
  "timestamp": "...",
  "status": 404,
  "error": "Resource not found",
  "message": "...",
  "path": "/users/1"
}
```

## 📊 Modelo de Domínio

- User
- Order
- Product
- Category
- OrderItem
- Payment

Relacionamentos:

- User → Orders (1:N)
- Order → OrderItem (1:N)
- Product ↔ Category (N:N)
- Order → Payment (1:1)

## 🎯 Objetivo

Consolidar conhecimentos em:

- Spring Boot
- APIs REST
- JPA/Hibernate
- Arquitetura backend profissional

## 📌 Melhorias Futuras

- Spring Security + JWT
- Paginação
- Swagger/OpenAPI
- Deploy em cloud
- Testes automatizados

## 👨‍💻 Autor

Desenvolvido por Fabricio Vianna

Projeto desenvolvido durante o curso "Java COMPLETO: Programação Orientada a Objetos + Projetos"  ministrado por Nelio Alves.
