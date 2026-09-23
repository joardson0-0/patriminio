# API de Gerenciamento de Patrimônio

## 📋 Descrição do projeto

Este projeto consiste em uma **API REST desenvolvida com Node.js e Express** para realizar o gerenciamento de patrimônios.

A API permite:

- Consultar os patrimônios cadastrados;
- Cadastrar um novo patrimônio;
- Excluir um patrimônio pelo seu ID;
- Alterar os dados de um patrimônio existente.

Os dados utilizados pela aplicação são armazenados inicialmente no arquivo `dados.json`.

---

## 🚀 Instalação e execução

### Pré-requisitos

Para executar o projeto, é necessário ter instalado:

- [Node.js](https://nodejs.org/)
- npm, que normalmente é instalado junto com o Node.js.

### 1. Clone o projeto

```bash
git clone <URL_DO_REPOSITORIO>

Entre na pasta do projeto:

cd nome-do-projeto

2. Instale as dependências
Execute:

npm install

Caso o Express ainda não esteja instalado:

npm install express

3. Execute a aplicação
Execute o arquivo principal do projeto:

node index.js

Caso o arquivo possua outro nome, substitua index.js pelo nome correspondente.

Ao iniciar corretamente, será exibida uma mensagem semelhante a:

Servidor: http://127.0.0.1:4000

A API estará disponível em:

http://127.0.0.1:4000

🛠️ Tecnologias utilizadas
Node.js — ambiente utilizado para executar JavaScript no servidor.

Express — framework utilizado para criação da API e definição das rotas.

JavaScript — linguagem utilizada no desenvolvimento.

JSON — formato utilizado para armazenamento dos dados.

HTTP/REST — padrão utilizado para comunicação com a API.

📁 Estrutura do projeto
projeto/
│
├── index.js
├── dados.json
├── package.json
├── package-lock.json
└── README.md

index.js
Arquivo responsável por:

Criar o servidor;

Configurar o Express;

Definir as rotas;

Receber as requisições;

Manipular os patrimônios.

dados.json
Arquivo utilizado para armazenar os dados iniciais dos patrimônios.

package.json
Arquivo que contém as configurações do projeto e suas dependências.

🔗 Rotas disponíveis
Método	Rota	Descrição
GET	/	Lista todos os patrimônios
POST	/	Cadastra um novo patrimônio
DELETE	/:id	Exclui um patrimônio pelo ID
PUT	/:id	Atualiza um patrimônio pelo ID

📥 Exemplos de requisições
1. Listar patrimônios
Requisição
GET http://127.0.0.1:4000/

cURL
curl http://127.0.0.1:4000/

Resposta
[
  {
    "id": 1,
    "item": "Notebook",
    "local": "Sala 01",
    "dataRegistro": "2026-09-20",
    "valor": 3500,
    "patrimonio": "PAT001"
  },
  {
    "id": 2,
    "item": "Monitor",
    "local": "Sala 02",
    "dataRegistro": "2026-09-21",
    "valor": 1200,
    "patrimonio": "PAT002"
  }
]

2. Cadastrar um patrimônio
Requisição
POST http://127.0.0.1:4000/
Content-Type: application/json

Corpo da requisição
{
  "id": 3,
  "item": "Teclado",
  "local": "Sala 03",
  "dataRegistro": "2026-09-23",
  "valor": 150,
  "patrimonio": "PAT003"
}

cURL
curl -X POST http://127.0.0.1:4000/ \
-H "Content-Type: application/json" \
-d "{\"id\":3,\"item\":\"Teclado\",\"local\":\"Sala 03\",\"dataRegistro\":\"2026-09-23\",\"valor\":150,\"patrimonio\":\"PAT003\"}"

Resposta
pedido recebido

3. Excluir um patrimônio
Para excluir um patrimônio, informe o id na URL.

Requisição
DELETE http://127.0.0.1:4000/3

cURL
curl -X DELETE http://127.0.0.1:4000/3

Resposta
pedido excluido com sucesso

4. Alterar um patrimônio
Para alterar um patrimônio, utilize o método PUT e informe o ID na URL.

Requisição
PUT http://127.0.0.1:4000/3
Content-Type: application/json

Corpo da requisição
{
  "id": 3,
  "item": "Teclado Mecânico",
  "local": "Sala 04",
  "dataRegistro": "2026-09-23",
  "valor": 250,
  "patrimonio": "PAT003"
}

cURL
curl -X PUT http://127.0.0.1:4000/3 \
-H "Content-Type: application/json" \
-d "{\"id\":3,\"item\":\"Teclado Mecânico\",\"local\":\"Sala 04\",\"dataRegistro\":\"2026-09-23\",\"valor\":250,\"patrimonio\":\"PAT003\"}"

Resposta
pedido atualizado

📊 Modelo dos dados
Cada patrimônio possui os seguintes campos:

Campo	Tipo	Descrição
id	Number	Identificador do patrimônio
item	String	Nome ou descrição do item
local	String	Local onde o item está armazenado
dataRegistro	String	Data de registro do patrimônio
valor	Number	Valor do patrimônio
patrimonio	String	Código de identificação patrimonial

Exemplo
{
  "id": 1,
  "item": "Notebook",
  "local": "Laboratório",
  "dataRegistro": "2026-09-23",
  "valor": 3500,
  "patrimonio": "PAT001"
}

🔄 Funcionamento da API
Cliente
   │
   ├── GET ──────► Listar patrimônios
   │
   ├── POST ─────► Cadastrar patrimônio
   │
   ├── PUT ──────► Alterar patrimônio
   │
   └── DELETE ───► Excluir patrimônio
                         │
                         ▼
                    dados.json

⚠️ Observações
Atualmente, os dados são carregados a partir do arquivo dados.json e manipulados em memória.

A aplicação não utiliza um banco de dados.

As alterações realizadas durante a execução do servidor não são gravadas permanentemente no arquivo dados.json.

Para uma aplicação maior, seria possível utilizar:

MySQL;

PostgreSQL;

MongoDB;

SQLite.

Também seria recomendável implementar:

Validação dos dados;

Tratamento de erros;

Códigos HTTP adequados;

Autenticação;

Banco de dados;

Documentação com Swagger.

🧪 Testando com Postman
A API pode ser testada utilizando o Postman.

GET
GET http://127.0.0.1:4000/

POST
POST http://127.0.0.1:4000/

Body → raw → JSON:

{
  "id": 4,
  "item": "Mouse",
  "local": "Escritório",
  "dataRegistro": "2026-09-23",
  "valor": 100,
  "patrimonio": "PAT004"
}

PUT
PUT http://127.0.0.1:4000/4

Body:

{
  "id": 4,
  "item": "Mouse sem fio",
  "local": "Escritório",
  "dataRegistro": "2026-09-23",
  "valor": 130,
  "patrimonio": "PAT004"
}

DELETE
DELETE http://127.0.0.1:4000/4

🐛 Correção importante no código
Na função responsável por alterar um patrimônio existe um pequeno erro:

if(pedidos.id == id) {

pedidos é um array. O correto é verificar o objeto pedido que está sendo percorrido pelo forEach:

if (pedido.id == id) {

A função corrigida fica:

const alterarPatrimonio = (req, res) => {
    const id = req.params.id;
    const dados = req.body;

    pedidos.forEach((pedido) => {
        if (pedido.id == id) {
            pedido.id = dados.id;
            pedido.item = dados.item;
            pedido.local = dados.local;
            pedido.dataRegistro = dados.dataRegistro;
            pedido.valor = dados.valor;
            pedido.patrimonio = dados.patrimonio;
        }
    });

    res.send("pedido atualizado");
};

📌 Resumo
Esta API implementa um CRUD básico para gerenciamento de patrimônios.

Operação	Método	Rota
Consultar	GET	/
Cadastrar	POST	/
Atualizar	PUT	/:id
Excluir	DELETE	/:id

O projeto utiliza Node.js, Express, JavaScript e JSON, servindo como uma base simples para uma aplicação de controle patrimonial.
