# 📚 Sistema de Gestão Escolar Relacional

Este projeto representa um sistema de banco de dados relacional completo para uma instituição de ensino, com foco em gestão acadêmica, administrativa e comunicação entre alunos, professores, responsáveis e direção.

---

## 🧩 Funcionalidades

- Cadastro de alunos, professores e responsáveis
- Controle de turmas, disciplinas, matrículas e provas
- Lançamento de notas por disciplina e bimestre
- Controle de frequência por data e matrícula
- Registro de atestados médicos (com justificativa de faltas)
- Registro de ocorrências escolares (disciplinares e elogios)
- Agendamento de eventos escolares (reuniões, feriados, etc.)
- Mensagens entre usuários (professores, responsáveis, administração)
- Armazenamento de documentos do aluno (histórico, boletim, etc.)
- Associação entre alunos e múltiplos responsáveis
- Perfis de acesso com controle por tipo de usuário

---

## 🧠 Estrutura de Tabelas

- `Usuario` – Login e perfil (aluno, responsável, professor, admin)
- `Aluno`, `Professor`, `Responsavel` – Perfis e dados pessoais
- `AlunoResponsavel` – Relação N:N entre alunos e responsáveis
- `Turma`, `Disciplina`, `Matricula` – Estrutura curricular
- `Nota`, `Frequencia`, `Prova` – Avaliações e presenças
- `AtestadoMedico` – Justificativas médicas
- `Ocorrencia` – Advertências e elogios
- `EventoEscolar` – Agenda institucional
- `Mensagem` – Comunicação interna
- `DocumentoAluno` – Arquivos/documentos associados ao aluno

---

## 🛠 Tecnologias recomendadas

- **SGBD**: MySQL
- **Frontend** (opcional): React, Next.js ou Vue.js
- **Backend** (opcional): Node.js (Express), Django, Laravel ou Spring
- **ORM** (opcional): Sequelize, Prisma, TypeORM, Eloquent, etc.

---

## 💡 Possíveis extensões futuras

- Controle financeiro e mensalidades
- Integração com plataforma EAD
- Avaliações por competências
- Painel de indicadores (dashboard)
- Backup e auditoria de dados

---

## 📎 Autor
**Vanessa Alves** – Projeto desenvolvido com foco acadêmico 
