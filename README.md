# Sobre

Microservice desenvolvido no [ignite lab](https://lp.rocketseat.com.br/inscricao/ignite-lab), evento de programação da [rocketseat](https://www.rocketseat.com.br/) com duração de 3 dias, focado na prática, essa edição o projeto foi um microservice de notificações.

## Ferramentas

  - [TypeScript](https://www.typescriptlang.org/)
  - [NodeJs](https://nodejs.org/pt-br/)
  - [NestJs](https://nestjs.com/)
  - [Prisma](https://www.prisma.io/)

## Tabela do Banco de dados

### Notification

| id | recipientId | content                 | category | readAt | canceledAt | createdAt |
|----|-------------|-------------------------|----------|--------|------------|-----------|
| 1  | 1           | 'new test Notification' | 'test'   | null   | null       |'2022-12-14T22:55:42.221Z'|
| 2  | 2           | 'new test Notification' | 'test'   | null   | null       |'2022-12-14T22:55:42.221Z'|
| 3  | 2           | 'new test Notification' | 'test'   | null   | null       |'2022-12-14T22:55:42.221Z'|

## Endpoints

> host = `http://localhost:3000/notifications` *é a rota padrão*

| Type | Route   |  Status Code |Body                               |       About           |
|------|---------|--------------|-----------------------------------|-----------------------|
| POST |`host`/        |  201         | { "notification": { "id": "9ff2fb36-52bd-4058-a5fc-bd6623f14da8", "content": "new test Notification", "category": "test", "recipientId": "5e458695-be54-4d2e-83a9-68197a33bf57" } }| Send notification|
| GET  | `host`/from/:recipientId  | 200 | { "notification": [{ "id": "9ff2fb36-52bd-4058-a5fc-bd6623f14da8", "content": "new test Notification", "category": "test", "recipientId": "5e458695-be54-4d2e-83a9-68197a33bf57" }, ...] }| Get recipients notification|
| GET  | `host`/count/from/:recipientId  | 200 | {"count": 8}| Count recipients notification|
| PATCH  | `host`/:id/cancel  | 200 || Cancel notification  |
| PATCH  | `host`/:id/read    | 200 || Read notification    |
| PATCH  | `host`/:id/unread  | 200 || Unread notification  |
