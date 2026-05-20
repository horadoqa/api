# Principais Termos em APIs

## API Integration

É o processo de conectar diferentes sistemas ou aplicações por meio de APIs para troca de dados e automação.

**Exemplo:**
Um e-commerce integrado à API dos Correios para calcular frete automaticamente.

---

## API Gateway

É uma camada intermediária que centraliza o gerenciamento das APIs, controlando autenticação, segurança, monitoramento e roteamento.

**Exemplo:**
Uma empresa usa um API Gateway para controlar acesso aos serviços de pagamento, usuários e pedidos em um único ponto.

---

## API Lifecycle

Representa todo o ciclo de vida de uma API: planejamento, desenvolvimento, testes, publicação, monitoramento e descontinuação.

**Exemplo:**
Uma fintech cria uma API, publica documentação, monitora uso e depois lança uma nova versão.

---

## Authentication

Processo de verificar a identidade do usuário ou sistema.

**Exemplo:**
Login com usuário e senha ou uso de token JWT.

---

## Authorization

Define o que o usuário autenticado pode acessar ou executar.

**Exemplo:**
Um usuário comum pode visualizar pedidos, mas apenas administradores podem excluí-los.

---

## CRUD

Conjunto das quatro operações básicas em sistemas:

* **Create** → Criar
* **Read** → Ler
* **Update** → Atualizar
* **Delete** → Excluir

**Exemplo:**
Cadastro de clientes em um sistema.

---

## Cache

Armazenamento temporário de dados para melhorar desempenho e reduzir consultas repetidas.

**Exemplo:**
Salvar resultados de uma consulta de produtos mais acessados.

---

## Client

Aplicação ou dispositivo que consome uma API.

**Exemplo:**
Um aplicativo mobile consumindo uma API de banco.

---

## Method

Define a ação realizada na API.

Os métodos mais comuns são:

* **GET** → Buscar dados
* **POST** → Criar dados
* **PUT** → Atualizar dados
* **DELETE** → Remover dados

**Exemplo:**
`GET https://serverest.dev/usuarios`

---

## Pagination

Técnica usada para dividir grandes volumes de dados em páginas menores.

**Exemplo:**
Mostrar 20 produtos por página em um marketplace.

---

## Payload

Conjunto de dados enviados em uma requisição ou resposta.

**Exemplo:**

```json
{
  "nome": "Hora do QA",
  "email": "horadoqa@email.com"
}
```

---

## Query Parameters

Parâmetros enviados na URL para filtrar ou modificar consultas.

**Exemplo:**

```bash
GET https://serverest.dev/usuarios?administrador=true
GET https://serverest.dev/produtos?nome=Logitech
```

---

## Rate Limiting

Controle da quantidade de requisições permitidas em determinado período.

**Exemplo:**
Máximo de 100 requisições por minuto por usuário.

> Quando o limite de requisições é excedido, a API retorna o código HTTP 429 (Too Many Requests).

---

## Request

Requisição enviada pelo cliente para a API.

**Exemplo:**

```bash
GET https://serverest.dev/usuarios
```

---

## Resource

Objeto ou entidade disponibilizada pela API.

**Exemplo:**

* `/usuarios`
* `/pedidos`
* `/produtos`

---

## Response

Resposta retornada pela API após uma requisição.

**Exemplo:**

```json
{
  "status": "sucesso",
  "mensagem": "Cliente criado"
}
```

---

## Response Code

Código HTTP que informa o resultado da operação.

Principais códigos:

* **200** → Sucesso
* **201** → Criado com sucesso
* **400** → Requisição inválida
* **401** → Não autenticado
* **403** → Acesso negado
* **404** → Não encontrado
* **500** → Erro interno do servidor

**Exemplo:**
Ao criar um usuário corretamente, a API retorna `201 Created`.
