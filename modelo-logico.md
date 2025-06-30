
# 📊 Modelo Lógico – Sistema de Gestão Escolar Relacional

Este documento apresenta o **modelo lógico** do banco de dados relacional do sistema de gestão escolar, com foco nas tabelas, chaves primárias (PK) e chaves estrangeiras (FK) — sem considerar ainda a linguagem de implementação (ex: SQL).

---

## 🧱 Tabelas e Relacionamentos

### 🔐 `Usuario`
- `id_usuario` (PK)
- `nome`
- `email`
- `senha_hash`
- `tipo_usuario` → aluno | professor | responsável | admin

---

### 👩‍🎓 `Aluno`
- `id_aluno` (PK)
- `nome`
- `data_nascimento`
- `id_usuario` (FK → Usuario)

### 👨‍🏫 `Professor`
- `id_professor` (PK)
- `nome`
- `disciplina`
- `id_usuario` (FK → Usuario)

### 👨‍👧 `Responsavel`
- `id_responsavel` (PK)
- `nome`
- `telefone`
- `email`
- `parentesco`

### 👪 `AlunoResponsavel` (Associação N:N)
- `id_aluno` (FK → Aluno)
- `id_responsavel` (FK → Responsavel)
- (PK composta: `id_aluno`, `id_responsavel`)

---

### 🏫 `Turma`
- `id_turma` (PK)
- `nome`
- `turno`
- `ano`

### 📚 `Disciplina`
- `id_disciplina` (PK)
- `nome`

### 🎓 `Matricula`
- `id_matricula` (PK)
- `id_aluno` (FK → Aluno)
- `id_turma` (FK → Turma)
- `data_matricula`

---

### 📝 `Nota`
- `id_nota` (PK)
- `id_matricula` (FK → Matricula)
- `id_disciplina` (FK → Disciplina)
- `bimestre`
- `valor`

### 📆 `Frequencia`
- `id_frequencia` (PK)
- `id_matricula` (FK → Matricula)
- `data`
- `presente` (booleano)

### 🩺 `AtestadoMedico`
- `id_atestado` (PK)
- `id_aluno` (FK → Aluno)
- `data_emissao`
- `data_entrega`
- `dias_afastado`
- `motivo`
- `arquivo_pdf`

---

### 🚦 `Ocorrencia`
- `id_ocorrencia` (PK)
- `id_aluno` (FK → Aluno)
- `data`
- `tipo` → disciplina | elogio
- `descricao`

### 📅 `EventoEscolar`
- `id_evento` (PK)
- `titulo`
- `data`
- `descricao`
- `tipo`

---

### ✉️ `Mensagem`
- `id_mensagem` (PK)
- `id_remetente` (FK → Usuario)
- `id_destinatario` (FK → Usuario)
- `data_envio`
- `conteudo`

### 📎 `DocumentoAluno`
- `id_documento` (PK)
- `id_aluno` (FK → Aluno)
- `tipo`
- `arquivo_pdf`
- `data_upload`

---

## 📌 Observações:
- Todas as chaves estrangeiras mantêm **integridade referencial**.
- Há **relacionamentos N:N** entre aluno e responsável.
- As tabelas são organizadas para permitir **expansão futura** (ex: financeiro, notificações).
