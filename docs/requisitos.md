# Requisitos do Sistema

Milestone: Requisitos

---

## Requisitos Funcionais (RF)

### RF01 - Cadastro de Usuário
O sistema deve permitir que um usuário realize cadastro informando nome, e-mail e senha.

**Critérios de Aceitação:**
- O usuário deve informar nome, e-mail válido e senha.
- O sistema deve validar formato do e-mail.
- O sistema deve impedir cadastro com e-mail já existente.
- Após cadastro válido, o usuário deve ser redirecionado para a tela inicial/logado automaticamente.

---

### RF02 - Login de Usuário
O sistema deve permitir que usuários cadastrados realizem login.

**Critérios de Aceitação:**
- O sistema deve autenticar usando e-mail e senha.
- O sistema deve exibir mensagem de erro para credenciais inválidas.
- O usuário autenticado deve acessar a área restrita.

---

### RF03 - Cadastro de Tarefa
O sistema deve permitir que usuários autenticados cadastrem tarefas.

**Critérios de Aceitação:**
- O usuário deve informar título e descrição.
- A tarefa deve ficar vinculada ao usuário logado.
- A tarefa deve ser salva no sistema e aparecer na listagem.

---

### RF04 - Listagem de Tarefas
O sistema deve permitir que o usuário visualize suas tarefas cadastradas.

**Critérios de Aceitação:**
- O sistema deve listar apenas tarefas do usuário autenticado.
- A listagem deve exibir título e status da tarefa.
- A listagem deve atualizar após criação ou exclusão de tarefa.

---

## Requisitos Não Funcionais (RNF)

### RNF01 - Desempenho
O sistema deve responder às requisições principais (login, cadastro e listagem) em até 2 segundos, considerando até 100 usuários simultâneos.

**Critério de Verificação:**
- Teste de carga simulando 100 usuários.
- Tempo médio de resposta ≤ 2 segundos.

---

### RNF02 - Segurança
As senhas dos usuários devem ser armazenadas de forma criptografada.

**Critério de Verificação:**
- Verificação no banco de dados de que as senhas não estão em texto puro.
- Uso de algoritmo de hash seguro (ex.: bcrypt ou equivalente).

---

## Regras de Negócio (RN)

### RN01 - E-mail Único
Não é permitido cadastrar dois usuários com o mesmo e-mail.

**Critério de Verificação:**
- Tentativa de cadastro com e-mail já existente deve retornar erro.

---

### RN02 - Exclusão Restrita
Um usuário só pode excluir tarefas que ele mesmo criou.

**Critério de Verificação:**
- Tentativa de exclusão de tarefa de outro usuário deve retornar erro de autorização.
