# CodePlay

Plataforma de jogos para aprender programação web, feita em equipe no curso técnico de Desenvolvimento de Sistemas do SENAI.

O aluno cria uma conta, escolhe uma trilha e resolve desafios escrevendo código de verdade em um editor dentro da página. Todos os desafios se passam em uma fazenda, e o progresso fica salvo por usuário.

## Trilhas

| Trilha | Nível 1 | Nível 2 | Nível 3 |
|---|---|---|---|
| Front-end | Flexbox básico | Flexbox avançado | CSS Grid |
| Back-end | Rotas com Express | CRUD de animais | Autenticação com JWT |
| Banco de dados | SQL básico | JOINs e relacionamentos | Chaves estrangeiras |

## Tecnologias

- **Interface:** React 19, Vite, React Router, Tailwind CSS e componentes Radix UI
- **Servidor:** Node.js com Express 5
- **Banco:** MySQL

## Como rodar

Precisa de Node.js 20+ e de um MySQL local.

1. Crie o banco importando o script:

   ```bash
   mysql -u root -p < "CodePlay - Front/src/components/database/codeplay.sql"
   ```

2. Ajuste usuário e senha do MySQL no início de `CodePlay - Front/server.js`.

3. Instale e suba interface e servidor juntos:

   ```bash
   cd "CodePlay - Front"
   npm install
   npm run dev
   ```

A interface abre em `http://localhost:3000` e a API em `http://localhost:3001`.

## Estrutura

```text
CodePlay - Front/
├── server.js                 API Express: cadastro, login, perfil e progresso
└── src/
    ├── App.jsx               Rotas da aplicação
    ├── components/
    │   ├── Dashboard.tsx     Painel com as trilhas e o progresso
    │   ├── games/            Os nove desafios (front, back e banco)
    │   ├── ui/               Editor de código, cabeçalho do jogo e componentes base
    │   └── database/         Script SQL do banco
    └── styles/
```

## Limitações conhecidas

É um projeto de curso que roda só em ambiente local, e algumas decisões não serviriam para produção:

- As senhas são gravadas em texto puro. O correto é guardar apenas o hash (bcrypt ou argon2).
- As credenciais do banco estão escritas em `server.js`. Deveriam vir de variáveis de ambiente.
- O login não emite token nem sessão, então as rotas da API não exigem autenticação.

## Equipe

Projeto desenvolvido em grupo. O repositório original é [MuriloGomesOli/CodePlay](https://github.com/MuriloGomesOli/CodePlay), e este é o meu espelho dele.

- [Murilo Gomes de Oliveira](https://github.com/MuriloGomesOli)
- [Daniel Augusto](https://github.com/danieelaugustoo)
- RaphaelLorenzo777
