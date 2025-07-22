# API de Equipes e Pilotos de F1

Este projeto é uma API simples desenvolvida com **Fastify** em **TypeScript**, que fornece informações sobre equipes e pilotos de Fórmula 1. Ideal para fins didáticos, testes ou como base para projetos maiores.

---

## 🚀 Funcionalidades

* Listagem de equipes de Fórmula 1
* Listagem de pilotos
* Busca de piloto por ID
* Suporte a CORS com origem aberta (`*`)
* Logger nativo do Fastify

---

## 📦 Tecnologias utilizadas

* [Fastify](https://www.fastify.io/)
* [TypeScript](https://www.typescriptlang.org/)
* [TSX](https://github.com/esbuild-kit/tsx)
* [Tsup](https://tsup.egoist.dev/)
* [@fastify/cors](https://github.com/fastify/fastify-cors)


## 📌 Requisitos

* Node.js 18+
* npm (ou yarn)

---

## ⚙️ Scripts disponíveis

| Comando               | Descrição                                   |
| --------------------- | ------------------------------------------- |
| `npm run start:dev`   | Inicia o servidor em modo desenvolvimento   |
| `npm run start:watch` | Inicia o servidor com hot-reload            |
| `npm run dist`        | Compila o código TypeScript para JavaScript |
| `npm run start:dist`  | Compila e executa o código compilado        |

---

## 🔌 Endpoints

### `GET /teams`

Retorna a lista de equipes.

#### Exemplo de resposta:

```json
{
  "teams": [
    { "id": 1, "name": "Mc Laren", "base": "Reino unido" },
    { "id": 2, "name": "Mercedez", "base": "Reino Unido" },
    { "id": 3, "name": "Red Bull Racing", "base": "Reino Unido" }
  ]
}
```

---

### `GET /drivers`

Retorna a lista de pilotos.

#### Exemplo de resposta:

```json
{
  "drivers": [
    { "id": 1, "name": "Max Verstappen", "team": "Red Bull Racing" },
    { "id": 2, "name": "Luis Hamilton", "team": "Mercedez" },
    { "id": 3, "name": "Lando Norris", "team": "Mc Laren" }
  ]
}
```

---

### `GET /drivers/:id`

Retorna os dados de um piloto específico com base no ID.

#### Exemplo de sucesso:

`GET /drivers/1`

```json
{
  "driver": {
    "id": 1,
    "name": "Max Verstappen",
    "team": "Red Bull Racing"
  }
}
```

#### Exemplo de erro (ID inexistente):

```json
{
  "message": "Driver not found"
}
```

---

## 🏁 Como rodar o projeto

1. Instale as dependências:

```bash
npm install
```

2. Execute o servidor em modo desenvolvimento:

```bash
npm run start:dev
```

3. Acesse os endpoints via `http://localhost:3333`.

---