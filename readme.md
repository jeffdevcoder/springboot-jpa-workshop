# Spring Boot JPA Workshop

API REST desenvolvida com **Spring Boot** e **Spring Data JPA**, como projeto de estudo sobre mapeamento objeto-relacional, relacionamentos entre entidades e construção de serviços web.

## Tecnologias

- Java 25
- Spring Boot 4.1.1
- Spring Web MVC
- Spring Data JPA (Hibernate)
- H2 Database (perfil de teste) + H2 Console
- PostgreSQL (perfil de desenvolvimento/produção)
- Maven

## Estrutura do projeto

```
src/main/java/com/educandoweb/course
├── entities      # Entidades JPA
├── repositories  # Interfaces Spring Data
├── services      # Regras de negócio
├── resources     # Controladores REST
└── config        # Configurações e carga inicial de dados
```

## Pré-requisitos

- JDK 25
- Git
- (Opcional) PostgreSQL, caso vá usar o perfil que o utiliza

O Maven não precisa estar instalado, pois o projeto inclui o Maven Wrapper (`mvnw`).

## Como executar

```bash
# clonar o repositório
git clone https://github.com/jeffdevcoder/springboot-jpa-workshop.git
cd springboot-jpa-workshop

# executar a aplicação (Linux/macOS)
./mvnw spring-boot:run

# executar a aplicação (Windows)
mvnw.cmd spring-boot:run
```

A aplicação sobe em `http://localhost:8080`.

### Banco de dados

- **H2 (em memória):** console disponível em `http://localhost:8080/h2-console`
    - JDBC URL: `jdbc:h2:mem:testdb` <!-- confirme no application.properties -->
    - Usuário: `sa` / Senha: em branco
- **PostgreSQL:** configure `spring.datasource.url`, `username` e `password` no arquivo de propriedades do perfil correspondente.

## Endpoints

| Método | Rota           | Descrição                |
| ------ | -------------- | ------------------------ |
| GET    | `/users`       | Lista todos os usuários  |
| GET    | `/users/{id}`  | Busca usuário por id     |
| POST   | `/users`       | Cria um usuário          |
| PUT    | `/users/{id}`  | Atualiza um usuário      |
| DELETE | `/users/{id}`  | Remove um usuário        |

## O que este projeto pratica

- Mapeamento de entidades com JPA (`@Entity`, `@ManyToOne`, `@OneToMany`, `@ManyToMany`)
- Chaves compostas (`@EmbeddedId`) e associações 1-para-1
- Repositórios com Spring Data JPA
- Camada de serviço e tratamento de exceções
- Perfis de configuração (teste e desenvolvimento)