# API

## O que é uma API?

**API** significa *Application Programming Interface* (Interface de Programação de Aplicações).
É um **conjunto de regras e padrões** que permite que diferentes softwares conversem entre si.

Em termos simples:

> 🔌 **Uma API é como um intermediário que permite que dois sistemas troquem informações de forma organizada e segura.**

---

## 📦 Exemplo do dia a dia

Imagine um restaurante:

* 👨‍🍳 A cozinha é o **sistema**
* 🧑‍💼 O garçom é a **API**
* 🍽️ Você é o **usuário**

Você não entra na cozinha para pegar sua comida.
Você faz o pedido ao garçom (API), ele leva à cozinha (sistema) e traz a resposta (resultado).

---

## 💻 Exemplo na prática (tecnologia)

Quando você usa um aplicativo que mostra previsão do tempo:

* O app faz uma **requisição** para uma API
* A API busca os dados no servidor
* Ela retorna as informações (temperatura, chuva, vento)

Outro exemplo comum são as APIs de pagamento como:

* Stripe
* PayPal

Elas permitem que lojas online processem pagamentos sem precisar criar um sistema financeiro do zero.

---

## 🔄 Como funciona uma API?

Geralmente segue este fluxo:

1. **Requisição (Request)** → Um sistema pede algo
2. **Processamento** → A API interpreta e encaminha
3. **Resposta (Response)** → A API devolve o resultado

Muitas APIs modernas usam o padrão **REST** e trocam dados no formato **JSON**.

---

## 🧩 Tipos comuns de API

* **APIs Web (REST / HTTP)** → Usadas na internet
* **APIs de bibliotecas** → Permitem usar funções prontas dentro de um código
* **APIs de sistemas operacionais** → Como as do Windows ou Android
* **APIs de terceiros** → Como:

  * Google (Google Maps API)
  * Meta (Instagram / Facebook APIs)

---

## 🎯 Por que APIs são importantes?

* Permitem integração entre sistemas
* Economizam tempo de desenvolvimento
* Facilitam automações
* Aumentam segurança (não é preciso expor o sistema inteiro)

---

Perfeito 👍 Vou mostrar um exemplo simples usando **Python** e depois **JavaScript**, simulando uma chamada a uma API pública.

---

# 🐍 Exemplo em Python (usando uma API pública)

Vamos usar a API pública **JSONPlaceholder**, que simula dados de posts.

### Código:

```python
import requests

url = "https://jsonplaceholder.typicode.com/posts/1"

resposta = requests.get(url)

if resposta.status_code == 200:
    dados = resposta.json()
    print("Título:", dados["title"])
    print("Conteúdo:", dados["body"])
else:
    print("Erro na requisição")
```

### 🔎 O que está acontecendo?

1. `requests.get(url)` → Faz a requisição para a API
2. A API responde com dados em formato **JSON**
3. `resposta.json()` → Converte o JSON em dicionário Python
4. Imprimimos os dados recebidos

---

# 🌐 Exemplo em JavaScript (usando fetch)

Agora o mesmo exemplo no navegador:

```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then(response => response.json())
  .then(data => {
    console.log("Título:", data.title);
    console.log("Conteúdo:", data.body);
  })
  .catch(error => console.error("Erro:", error));
```

### 🔎 O que acontece aqui?

1. `fetch()` → Envia uma requisição HTTP
2. `.json()` → Converte a resposta para objeto JavaScript
3. Exibimos os dados no console

---

### 🔁 Fluxo real da comunicação

Aplicação → 🌍 API → 🗄️ Banco de Dados → API → Aplicação

---

## Como testar APIs com ferramentas como Postman ?

Ótima pergunta 👍 Testar APIs com o **Postman** é uma das formas mais práticas de entender como elas funcionam.

---

## 🚀 O que é o Postman?

![Image](https://assets.postman.com/postman-docs/v11/postman-ui-v11-42.jpg)

![Image](https://toolsqa.com/gallery/Postman/1.Postman%20Navigation.png)

![Image](https://assets.postman.com/postman-docs/v11/response-pane-search-v11-35-4.jpg)

![Image](https://assets.postman.com/postman-docs/v11/documentation-including-examples-v11-1.jpg)

O **Postman** é uma ferramenta que permite:

* Enviar requisições HTTP (GET, POST, PUT, DELETE)
* Visualizar respostas da API
* Testar autenticação
* Organizar testes em coleções
* Automatizar testes

Ele funciona como um “laboratório” para APIs.

---

# 🧪 Passo a passo: Testando uma API (GET)

Vamos usar a API pública:

```
https://jsonplaceholder.typicode.com/posts/1
```

### ✅ 1. Abra o Postman

Clique em **New → HTTP Request**

### ✅ 2. Escolha o método

Selecione **GET**

### ✅ 3. Cole a URL

No campo de URL, cole:

```
https://jsonplaceholder.typicode.com/posts/1
```

### ✅ 4. Clique em "Send"

---

## 📥 O que você verá na resposta?

Você receberá algo assim:

```json
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati",
  "body": "quia et suscipit..."
}
```

### 🔎 O que observar:

* **Status** → 200 OK (significa sucesso)
* **Body** → Conteúdo retornado
* **Headers** → Informações técnicas da resposta
* **Tempo de resposta** → Velocidade da API

---

# 📤 Testando envio de dados (POST)

Agora vamos simular o envio de dados.

### 1️⃣ Mude o método para **POST**

URL:

```
https://jsonplaceholder.typicode.com/posts
```

### 2️⃣ Vá em "Body"

* Selecione **raw**
* Escolha **JSON**
* Cole:

```json
{
  "title": "Meu Post",
  "body": "Aprendendo API",
  "userId": 1
}
```

### 3️⃣ Clique em "Send"

Você verá uma resposta simulando a criação do recurso:

```json
{
  "title": "Meu Post",
  "body": "Aprendendo API",
  "userId": 1,
  "id": 101
}
```

---

# 🔐 Testando autenticação

Se a API exigir autenticação:

1. Vá na aba **Authorization**
2. Escolha o tipo:

   * Bearer Token
   * Basic Auth
   * OAuth 2.0
3. Insira as credenciais

Exemplo de header manual:

```
Authorization: Bearer SEU_TOKEN_AQUI
```

---

# 📦 Organizando com Collections

Você pode:

* Criar **Collections**
* Salvar requisições
* Criar variáveis (ex: {{base_url}})
* Automatizar testes

Isso é muito usado por times de backend e QA.

---

# 🎯 Dicas Profissionais

* Sempre verifique o **status code**
* Teste casos de erro (ex: ID inexistente)
* Use variáveis de ambiente (dev, staging, produção)
* Automatize testes com a aba **Tests**

---
