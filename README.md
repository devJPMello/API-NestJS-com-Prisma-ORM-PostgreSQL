# 📚 API NestJS - ClasseDeAula e Aluno

API RESTful desenvolvida com NestJS, Prisma ORM e PostgreSQL (NeonDB), com dois domínios principais:

- **ClasseDeAula**: nome e descrição
- **Aluno**: nome, e-mail e vínculo com uma classe

---

## 🚀 Tecnologias

- [NestJS](https://nestjs.com/)
- [Prisma ORM](https://www.prisma.io/)
- [PostgreSQL (NeonDB)](https://neon.tech/)
- [TypeScript](https://www.typescriptlang.org/)

---

## ⚙️ Instalação

1. Clone o repositório:

```bash
git clone https://github.com/seu-usuario/seu-projeto.git
cd seu-projeto
```

2. Instale as dependências:

```bash
npm install
```

3. Configure a variável de ambiente no arquivo `.env`:

```
DATABASE_URL="postgresql://USUARIO:SENHA@HOST/neondb?sslmode=require"
```

---

## 🛠️ Migrations e Seed

1. Crie o banco de dados e rode as migrations:

```bash
npx prisma migrate dev --name init
```

2. Popule o banco com dados iniciais:

```bash
npx prisma db seed
```

---

## ▶️ Rodando a aplicação

```bash
npm run start:dev
```

Servidor disponível por padrão em:  
👉 `http://localhost:3000`

---

## 📌 Endpoints

### ClasseDeAula

- `POST /classe`: criar nova classe  
- `GET /classe`: listar todas as classes

### Aluno

- `POST /aluno`: criar aluno vinculado a uma classe  
- `GET /aluno`: listar todos os alunos com nome da classe

---

## 🧼 Resetar base de dados

Durante desenvolvimento, para resetar os dados:

```ts
await prisma.aluno.deleteMany();
await prisma.classeDeAula.deleteMany();
```

Essas linhas já estão incluídas no `prisma/seed.ts`.
