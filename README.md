# Forum Hub API

Uma API REST para gerenciamento de fórum de discussão, desenvolvida com Spring Boot 3, oferecendo funcionalidades de CRUD para tópicos, autenticação JWT e documentação Swagger.

## 🚀 Funcionalidades

- Autenticação e Autorização com JWT
- CRUD completo de Tópicos
- Sistema de Respostas
- Paginação e Ordenação
- Documentação com Swagger
- Migrations com Flyway
- Persistência com Spring Data JPA

## 🛠️ Tecnologias

- Java 17
- Spring Boot 3
- Spring Security
- JWT
- Spring Data JPA
- MySQL/PostgreSQL
- Flyway Migration
- Swagger/OpenAPI
- Lombok
- BCrypt

## 📋 Requisitos

- Java 17+
- Maven
- MySQL/PostgreSQL

## 🔧 Configuração

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/Java-Spring_Boot-Challenge_Forum_Hub.git
cd Java-Spring_Boot-Challenge_Forum_Hub
```

2. Configure o banco de dados em `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/forum
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
```

3. Execute as migrations:
As migrations serão executadas automaticamente ao iniciar a aplicação, criando as seguintes tabelas:
- Perfis (V7)
- Usuários Perfis (V8)
- Cursos (V9)
- Tópicos (V10)
- Respostas (V11)
- Dados iniciais de perfis (V12)
- Dados iniciais de cursos (V13)

4. Compile e execute o projeto:
```bash
mvn spring-boot:run
```

## 🔐 Autenticação

A API utiliza autenticação JWT (JSON Web Token). Para acessar endpoints protegidos:

1. Faça login através do endpoint `/auth` com suas credenciais
2. Utilize o token retornado no header `Authorization` das requisições:
```
Authorization: Bearer seu_token_jwt
```

## 🌐 Endpoints

### Públicos
- `POST /auth` - Autenticação de usuários
- `POST /usuarios` - Cadastro de novos usuários

### Protegidos (Requer autenticação)
- `GET /topicos` - Lista todos os tópicos
- `GET /topicos/{id}` - Retorna um tópico específico
- `POST /topicos` - Cria um novo tópico
- `PUT /topicos/{id}` - Atualiza um tópico
- `DELETE /topicos/{id}` - Remove um tópico
- `POST /respostas` - Adiciona uma resposta a um tópico

## 📖 Documentação

A documentação completa da API está disponível através do Swagger UI:

- Swagger UI: http://localhost:8080/swagger-ui/index.html
- OpenAPI JSON: http://localhost:8080/v3/api-docs

## 🗃️ Estrutura do Projeto

```
src/main/java/br/com/alura/forum/
├── config/
│   └── security/         # Configurações de segurança e JWT
├── controller/           # Controllers REST
│   ├── dto/             # Objetos de transferência de dados
│   └── form/            # Objetos de entrada de dados
├── model/               # Entidades JPA
├── repository/          # Interfaces de repositório
└── service/            # Lógica de negócios

src/main/resources/
└── db/migration/        # Scripts de migração Flyway
```

## 🧪 Testes

Para executar os testes:
```bash
mvn test
```
Documentação swagger
![image](https://github.com/user-attachments/assets/54a67303-50bc-4914-a0ea-fd4eba1bc5d5)


## 📬 Contribuindo

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## ✨ Agradecimentos

- Alura
- Spring Boot Team
- Comunidade Open Source
