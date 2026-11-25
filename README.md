
# 💊 Farmácia — API REST

![Java](https://img.shields.io/badge/Java-17-orange?style=flat-square&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4-6DB33F?style=flat-square&logo=springboot)
![JWT](https://img.shields.io/badge/Auth-JWT-black?style=flat-square&logo=jsonwebtokens)

🖥️ **Front-end:** [farmacia-web](https://github.com/ThiagoTasseli/farmacia-web)

🔗 **Link de Teste da API:**  [https://projeto-final-bloco-02-7l9p.onrender.com](https://projeto-final-bloco-02-7l9p.onrender.com)

🔐 **Acesso Padrão:**  
- **Usuário:** `root@root.com`  
- **Senha:** `rootroot`

---

Este projeto é um sistema de **comércio eletrônico de uma farmácia**, desenvolvido como atividade prática do **bootcamp Web-Java**. A aplicação foi criada com **Spring Boot**, seguindo as boas práticas de desenvolvimento em camadas, integração com banco de dados relacional e implementação de autenticação com **JWT (JSON Web Token)** via **Spring Security**.

## 🚀 Funcionalidades

### ✅ Categoria
- 🔍 `GET /categorias` - Lista todas as categorias  
- 🔍 `GET /categorias/{id}` - Busca uma categoria por ID  
- 🔍 `GET /categorias/nome/{nome}` - Busca categorias pelo nome  
- ➕ `POST /categorias` - Cria uma nova categoria  
- ✏️ `PUT /categorias` - Atualiza uma categoria existente  
- ❌ `DELETE /categorias/{id}` - Deleta uma categoria por ID  

### ✅ Produto
- 🔍 `GET /produtos` - Lista todos os produtos  
- 🔍 `GET /produtos/{id}` - Busca um produto por ID  
- 🔍 `GET /produtos/nome/{nome}` - Busca produtos pelo nome  
- ➕ `POST /produtos` - Cria um novo produto (relacionado com uma categoria)  
- ✏️ `PUT /produtos` - Atualiza um produto existente  
- ❌ `DELETE /produtos/{id}` - Deleta um produto por ID  

### 🔐 Autenticação (Spring Security + JWT)
- 👤 `POST /usuarios/cadastrar` - Cadastro de usuário  
- 🔑 `POST /usuarios/logar` - Login e geração de token JWT  
- 🔒 Todas as rotas de Produto e Categoria são protegidas, exigindo token para acesso.

---

## 🛠 Tecnologias Utilizadas

- **Java 17**  
- **Spring Boot 3**  
- **Spring Web**  
- **Spring Data JPA**  
- **Spring Security**  
- **JWT (Json Web Token)**  
- **MySQL** (desenvolvimento) / **PostgreSQL** (produção)
- **SpringDoc (Swagger)**
- **Insomnia/Postman** (testes de API)

---

## 🔗 Relacionamento entre Entidades

O projeto possui o seguinte relacionamento entre as entidades:

- Uma **Categoria** pode conter **muitos Produtos** (OneToMany)  
- Cada **Produto** pertence a uma única **Categoria** (ManyToOne)

---

## ▶️ Como rodar localmente

```bash
git clone https://github.com/ThiagoTasseli/farmacia-api.git
cd farmacia-api

# Perfil dev usa MySQL local (db_farmacia, criado automaticamente)
export DB_PASSWORD=sua_senha_mysql
export JWT_SECRET=$(openssl rand -base64 32)   # opcional em dev

./mvnw spring-boot:run -Dspring-boot.run.profiles=dev
```

Em produção (perfil `prod`), configure `POSTGRESHOST`, `POSTGRESPORT`, `POSTGRESDATABASE`, `POSTGRESUSER`, `POSTGRESPASSWORD` e `JWT_SECRET`.

---

## 📁 Organização das Branches

| Branch | Descrição |
|--------|-----------|
| `main` | Versão final do projeto |
| `01_Configurando_Projeto` | Configuração inicial do projeto e banco de dados |
| `02_CRUD_Categoria` | CRUD completo da entidade Categoria |
| `03_CRUD_Produto_Relacionamento` | CRUD da entidade Produto + Relacionamento com Categoria |
| `04_Extras` | Implementações extras como autenticação JWT |

---

## 🔐 Autenticação com JWT

Para acessar as rotas protegidas:

1. Cadastre um usuário com `POST /usuarios/cadastrar`  
2. Faça login com `POST /usuarios/logar` e copie o token  
3. Nas requisições protegidas, adicione o token no header:  
   ```
   Authorization: Bearer <seu_token_aqui>
   ```

---

## 📬 Contato

Desenvolvido por [**Thiago Tasseli**](https://github.com/ThiagoTasseli)

Fique à vontade para tirar dúvidas, dar sugestões ou contribuir! 😄
