# Casos de Uso — Sistema de Gestão de Academia

Documento contendo a especificação dos **Casos de Uso** do sistema de gestão de academia.

---

## UC01 — Cadastrar Aluno

### **Ator Principal**
Recepcionista

### **Objetivo**
Permitir registrar um novo aluno no sistema.

### **Pré-condições**
- O recepcionista deve estar autenticado no sistema.

### **Pós-condições**
- Aluno cadastrado e disponível para contratação de plano.

### **Fluxo Principal**
1. O recepcionista acessa a tela de cadastro de alunos.  
2. O recepcionista preenche dados pessoais, contato, endereço e plano.  
3. O sistema valida os dados inseridos.  
4. O sistema salva o cadastro do aluno.

### **Fluxos Alternativos**
**A1 — Dados obrigatórios não preenchidos**  
- O sistema exibe mensagem solicitando preenchimento dos campos.

**A2 — CPF já cadastrado**  
- O sistema informa que já existe um aluno registrado.

### **RF Relacionados**
- RF01 — Cadastro de Alunos

### **RNF Relacionados**
- RNF02 — Segurança  
- RNF04 — Usabilidade

### **RN Relacionadas**
- RN06 — Acesso restrito por perfil

---

## UC02 — Atualizar Dados do Aluno

### **Ator Principal**
Recepcionista

### **Objetivo**
Permitir a atualização das informações cadastrais do aluno.

### **Pré-condições**
- Aluno deve estar previamente cadastrado.

### **Pós-condições**
- Dados do aluno atualizados no sistema.

### **Fluxo Principal**
1. Recepcionista acessa cadastro do aluno.  
2. Recepcionista altera informações desejadas.  
3. Sistema valida os dados atualizados.  
4. Sistema salva as alterações.

### **Fluxos Alternativos**
**A1 — Dados inválidos**  
- Sistema exibe erro de validação.

### **RF Relacionados**
- RF01 — Cadastro de Alunos

### **RNF Relacionados**
- RNF02 — Segurança  
- RNF04 — Usabilidade

### **RN Relacionadas**
- RN06 — Acesso restrito por perfil

---

## UC03 — Registrar Pagamento

### **Ator Principal**
Recepcionista

### **Objetivo**
Registrar pagamento da mensalidade do aluno.

### **Pré-condições**
- Aluno deve possuir plano ativo.

### **Pós-condições**
- Pagamento registrado e situação do aluno atualizada.

### **Fluxo Principal**
1. Recepcionista acessa tela de pagamentos.  
2. Recepcionista seleciona aluno.  
3. Recepcionista registra pagamento (dinheiro, cartão ou PIX).  
4. Sistema registra pagamento e atualiza situação do aluno.

### **Fluxos Alternativos**
**A1 — Tentativa de pagamento parcial**  
- Sistema bloqueia operação.

### **RF Relacionados**
- RF03 — Controle de Pagamentos

### **RNF Relacionados**
- RNF02 — Segurança  
- RNF03 — Performance

### **RN Relacionadas**
- RN04 — Pagamento parcial não permitido  
- RN07 — Atualização automática da regularidade

---

## UC04 — Verificar Regularidade do Aluno

### **Ator Principal**
Sistema

### **Objetivo**
Verificar automaticamente se o aluno está com pagamento em dia.

### **Pré-condições**
- Aluno cadastrado e plano ativo.

### **Pós-condições**
- Situação do aluno atualizada.

### **Fluxo Principal**
1. Sistema verifica data de vencimento da mensalidade.  
2. Sistema compara com pagamentos registrados.  
3. Sistema define status do aluno (regular ou inadimplente).

### **Fluxos Alternativos**
**A1 — Pagamento vencido**  
- Sistema marca aluno como inadimplente.

### **RF Relacionados**
- RF04 — Regularidade do Aluno

### **RNF Relacionados**
- RNF03 — Performance

### **RN Relacionadas**
- RN01 — Bloqueio por inadimplência

---

## UC05 — Validar Acesso na Catraca

### **Ator Principal**
Sistema de Catraca

### **Objetivo**
Validar entrada do aluno na academia.

### **Pré-condições**
- Aluno deve possuir identificação RFID.

### **Pós-condições**
- Entrada liberada ou bloqueada.

### **Fluxo Principal**
1. Aluno aproxima cartão RFID da catraca.  
2. Sistema recebe identificação do aluno.  
3. Sistema verifica regularidade.  
4. Sistema libera entrada.

### **Fluxos Alternativos**
**A1 — Aluno inadimplente**  
- Sistema bloqueia acesso.

**A2 — RFID não reconhecido**  
- Sistema exibe erro.

### **RF Relacionados**
- RF05 — Controle de Acesso

### **RNF Relacionados**
- RNF03 — Performance  
- RNF06 — Integração

### **RN Relacionadas**
- RN01 — Bloqueio por inadimplência

---

## UC06 — Agendar Aula

### **Ator Principal**
Aluno

### **Objetivo**
Permitir reservar vaga em aula disponível.

### **Pré-condições**
- Aluno deve estar ativo e regular.

### **Pós-condições**
- Reserva registrada no sistema.

### **Fluxo Principal**
1. Aluno acessa lista de aulas disponíveis.  
2. Aluno seleciona aula.  
3. Sistema verifica disponibilidade de vagas.  
4. Sistema confirma agendamento.

### **Fluxos Alternativos**
**A1 — Aula lotada**  
- Sistema bloqueia agendamento.

### **RF Relacionados**
- RF06 — Agendamento de Aulas

### **RNF Relacionados**
- RNF04 — Usabilidade

### **RN Relacionadas**
- RN02 — Limite de vagas

---

## UC07 — Cancelar Agendamento de Aula

### **Ator Principal**
Aluno

### **Objetivo**
Permitir cancelamento de reserva em aula.

### **Pré-condições**
- Aluno deve possuir agendamento ativo.

### **Pós-condições**
- Reserva removida do sistema.

### **Fluxo Principal**
1. Aluno acessa seus agendamentos.  
2. Aluno seleciona aula.  
3. Aluno solicita cancelamento.  
4. Sistema remove reserva.

### **Fluxos Alternativos**
**A1 — Prazo expirado**  
- Sistema bloqueia cancelamento.

### **RF Relacionados**
- RF06 — Agendamento de Aulas

### **RNF Relacionados**
- RNF04 — Usabilidade

### **RN Relacionadas**
- RN03 — Cancelamento até 1 hora antes

---

## UC11 — Criar Plano de Academia

### **Ator Principal**
Gerente

### **Objetivo**
Permitir a criação de novos planos de academia.

### **Pré-condições**
- Gerente autenticado no sistema.

### **Pós-condições**
- Plano cadastrado e disponível para contratação.

### **Fluxo Principal**
1. Gerente acessa o módulo de planos.  
2. Gerente seleciona a opção de criar plano.  
3. Gerente informa nome, valor, duração e características.  
4. Sistema valida os dados.  
5. Sistema salva o novo plano.

### **Fluxos Alternativos**
**A1 — Dados incompletos**  
- Sistema solicita preenchimento dos campos obrigatórios.

### **RF Relacionados**
- RF02 — Gerenciamento de Planos

### **RNF Relacionados**
- RNF04 — Usabilidade

### **RN Relacionadas**
- RN06 — Acesso restrito por perfil

<img width="567" height="481" alt="image" src="https://github.com/user-attachments/assets/c10cbea9-11f8-4b35-92ac-61022be48c15" />

### Atividade 11 — Criar Plano de Academia
Esta atividade representa o fluxo de criação de novos planos de academia. O gerente acessa o módulo de planos, insere os dados necessários e o sistema valida. Se os dados forem válidos, o plano é salvo e disponibilizado para contratação; caso contrário, o sistema solicita correção.
---

## UC12 — Editar Plano

### **Ator Principal**
Gerente

### **Objetivo**
Permitir a alteração das informações de um plano existente.

### **Pré-condições**
- Plano deve estar cadastrado no sistema.

### **Pós-condições**
- Informações do plano atualizadas.

### **Fluxo Principal**
1. Gerente acessa lista de planos.  
2. Gerente seleciona um plano.  
3. Gerente altera informações desejadas.  
4. Sistema valida dados.  
5. Sistema salva alterações.

### **Fluxos Alternativos**
**A1 — Dados inválidos**  
- Sistema exibe erro e solicita correção.

### **RF Relacionados**
- RF02 — Gerenciamento de Planos

### **RNF Relacionados**
- RNF04 — Usabilidade

### **RN Relacionadas**
- RN06 — Acesso restrito por perfil

<img width="456" height="481" alt="image" src="https://github.com/user-attachments/assets/8eb59829-fba5-4ed8-970d-1a84d61af0c8" />

### Atividade 12 — Editar Plano
Esta atividade descreve a edição de planos existentes. O gerente seleciona um plano, altera informações e o sistema valida. Se os dados forem válidos, as alterações são salvas; se inválidos, o sistema solicita correção.

---

## UC13 — Ativar Plano

### **Ator Principal**
Gerente

### **Objetivo**
Permitir ativar um plano para contratação.

### **Pré-condições**
- Plano previamente cadastrado.

### **Pós-condições**
- Plano disponível para uso.

### **Fluxo Principal**
1. Gerente acessa lista de planos.  
2. Gerente seleciona plano inativo.  
3. Gerente solicita ativação.  
4. Sistema altera status para ativo.

### **Fluxos Alternativos**
**A1 — Plano já ativo**  
- Sistema informa que o plano já está disponível.

### **RF Relacionados**
- RF02 — Gerenciamento de Planos

### **RNF Relacionados**
- RNF04 — Usabilidade

### **RN Relacionadas**
- RN06 — Acesso restrito por perfil

<img width="469" height="367" alt="image" src="https://github.com/user-attachments/assets/f84e999e-6cd5-4234-a7ba-13adede6c667" />

### Atividade 13 — Ativar Plano
Esta atividade mostra o processo de ativação de um plano inativo. O gerente solicita ativação e o sistema altera o status para ativo. Se o plano já estiver ativo, o sistema apenas informa.

---

## UC14 — Desativar Plano

### **Ator Principal**
Gerente

### **Objetivo**
Permitir desativar um plano existente.

### **Pré-condições**
- Plano cadastrado no sistema.

### **Pós-condições**
- Plano indisponível para novas contratações.

### **Fluxo Principal**
1. Gerente acessa lista de planos.  
2. Gerente seleciona plano ativo.  
3. Gerente solicita desativação.  
4. Sistema altera status para inativo.

### **Fluxos Alternativos**
**A1 — Plano já inativo**  
- Sistema informa que o plano já está desativado.

### **RF Relacionados**
- RF02 — Gerenciamento de Planos

### **RNF Relacionados**
- RNF04 — Usabilidade

### **RN Relacionadas**
- RN06 — Acesso restrito por perfil

<img width="483" height="367" alt="image" src="https://github.com/user-attachments/assets/739201fc-2293-4e72-90c2-ba80adca5876" />

### Atividade 14 — Desativar Plano
Esta atividade trata da desativação de planos ativos. O gerente solicita a desativação e o sistema altera o status para inativo. Se o plano já estiver inativo, o sistema informa.

---

## UC15 — Consultar Horários de Aula

### **Ator Principal**
Aluno

### **Objetivo**
Visualizar aulas disponíveis e horários.

### **Pré-condições**
- Aluno autenticado.

### **Pós-condições**
- Lista de aulas exibida.

### **Fluxo Principal**
1. Aluno acessa módulo de aulas.  
2. Sistema consulta aulas cadastradas.  
3. Sistema exibe horários e vagas disponíveis.

### **Fluxos Alternativos**
**A1 — Nenhuma aula disponível**  
- Sistema informa que não há aulas cadastradas.

### **RF Relacionados**
- RF06 — Agendamento de Aulas

### **RNF Relacionados**
- RNF04 — Usabilidade

### **RN Relacionadas**
- RN02 — Limite de vagas

<img width="517" height="312" alt="image" src="https://github.com/user-attachments/assets/857a91e2-c05a-4c30-8b20-6880018f5ee0" />

### Atividade 15 — Consultar Horários de Aula
Esta atividade permite ao aluno visualizar aulas disponíveis. O sistema consulta os registros e exibe horários e vagas. Se não houver aulas cadastradas, informa a ausência.

---

## UC16 — Enviar Notificação de Vencimento

### **Ator Principal**
Sistema

### **Objetivo**
Notificar o aluno sobre vencimento da mensalidade.

### **Pré-condições**
- Mensalidade próxima do vencimento.

### **Pós-condições**
- Notificação enviada.

### **Fluxo Principal**
1. Sistema verifica datas de vencimento.  
2. Sistema identifica mensalidades próximas.  
3. Sistema envia notificação ao aluno.

### **Fluxos Alternativos**
**A1 — Falha no envio**  
- Sistema registra tentativa e agenda novo envio.

### **RF Relacionados**
- RF10 — Notificações

### **RNF Relacionados**
- RNF01 — Disponibilidade

### **RN Relacionadas**
- RN01 — Bloqueio por inadimplência

<img width="322" height="396" alt="image" src="https://github.com/user-attachments/assets/2ba5aa87-4352-4622-84ee-269b50d3d3a0" />

### Atividade 16 — Enviar Notificação de Vencimento
Esta atividade descreve o envio automático de notificações de vencimento de mensalidade. O sistema verifica datas, identifica vencimentos próximos e envia notificações. Em caso de falha, registra a tentativa e agenda novo envio.

---

## UC17 — Enviar Confirmação de Agendamento

### **Ator Principal**
Sistema

### **Objetivo**
Confirmar agendamento de aula ao aluno.

### **Pré-condições**
- Agendamento realizado.

### **Pós-condições**
- Notificação enviada.

### **Fluxo Principal**
1. Sistema registra agendamento.  
2. Sistema gera mensagem.  
3. Sistema envia notificação.

### **Fluxos Alternativos**
**A1 — Falha na notificação**  
- Sistema registra erro.

### **RF Relacionados**
- RF10 — Notificações

### **RNF Relacionados**
- RNF01 — Disponibilidade

### **RN Relacionadas**
- RN02 — Limite de vagas

<img width="224" height="396" alt="image" src="https://github.com/user-attachments/assets/dbedefd3-536c-49fe-885e-a6d48624ba52" />

### Atividade 17 — Enviar Confirmação de Agendamento
Esta atividade confirma ao aluno o agendamento de uma aula. O sistema registra o agendamento, gera mensagem e envia notificação. Se houver falha, registra o erro.

---

## UC18 — Enviar Notificação de Nova Avaliação

### **Ator Principal**
Sistema

### **Objetivo**
Informar sobre nova avaliação física.

### **Pré-condições**
- Avaliação registrada.

### **Pós-condições**
- Notificação enviada.

### **Fluxo Principal**
1. Sistema detecta nova avaliação.  
2. Sistema gera mensagem.  
3. Sistema envia notificação.

### **Fluxos Alternativos**
**A1 — Falha no envio**  
- Sistema registra tentativa.

### **RF Relacionados**
- RF10 — Notificações

### **RNF Relacionados**
- RNF01 — Disponibilidade

### **RN Relacionadas**
- RN05 — Avaliação física

<img width="404" height="367" alt="image" src="https://github.com/user-attachments/assets/248520f7-276c-486c-84ed-07d88bee54c7" />

### Atividade 18 — Enviar Notificação de Nova Avaliação
Esta atividade informa ao aluno sobre uma nova avaliação física registrada. O sistema gera mensagem e envia notificação. Se houver falha, registra a tentativa de envio.

---

## UC19 — Consultar Histórico de Acessos

### **Ator Principal**
Gerente

### **Objetivo**
Visualizar histórico de entradas.

### **Pré-condições**
- Registros existentes.

### **Pós-condições**
- Histórico exibido.

### **Fluxo Principal**
1. Gerente acessa relatórios.  
2. Seleciona relatório de acessos.  
3. Sistema consulta dados.  
4. Sistema exibe histórico.

### **Fluxos Alternativos**
**A1 — Nenhum registro encontrado**  
- Sistema informa ausência de dados.

### **RF Relacionados**
- RF09 — Relatórios Gerenciais

### **RNF Relacionados**
- RNF03 — Performance

### **RN Relacionadas**
- RN06 — Acesso restrito por perfil

<img width="410" height="367" alt="image" src="https://github.com/user-attachments/assets/78f443a2-c1aa-413f-9fba-c3746672aa39" />

### Atividade 19 — Consultar Histórico de Acessos
Esta atividade permite ao gerente consultar o histórico de entradas dos alunos. O sistema busca os registros e exibe os dados. Se não houver registros, informa a ausência.


---

## UC20 — Consultar Ocupação das Aulas

### **Ator Principal**
Gerente

### **Objetivo**
Visualizar taxa de ocupação das aulas.

### **Pré-condições**
- Aulas cadastradas.

### **Pós-condições**
- Relatório exibido.

### **Fluxo Principal**
1. Gerente acessa relatórios.  
2. Seleciona ocupação de aulas.  
3. Sistema calcula vagas preenchidas.  
4. Sistema exibe resultados.

### **Fluxos Alternativos**
**A1 — Falha no processamento**  
- Sistema exibe erro.

### **RF Relacionados**
- RF09 — Relatórios Gerenciais

### **RNF Relacionados**
- RNF03 — Performance

### **RN Relacionadas**
- RN02 — Limite de vagas

<img width="359" height="367" alt="image" src="https://github.com/user-attachments/assets/4974a6c0-abef-4540-b6a0-a7634a281879" />

### Atividade 20 — Consultar Ocupação das Aulas
Esta atividade mostra ao gerente a taxa de ocupação das aulas. O sistema calcula vagas preenchidas e exibe resultados. Se houver falha no processamento, informa o erro.

---

# Descrição dos Casos de Uso

## 3. Casos de Uso

### UC01 — Cadastrar Aluno
Ator Principal: Recepcionista  
Objetivo: Registrar um novo aluno no sistema.  
Pré-condições: Recepcionista autenticado.  
Pós-condições: Aluno cadastrado.

---

### UC02 — Atualizar Dados do Aluno
Ator Principal: Recepcionista  
Objetivo: Atualizar informações cadastrais do aluno.  
Pré-condições: Aluno cadastrado.  
Pós-condições: Dados atualizados.

---

### UC03 — Registrar Pagamento
Ator Principal: Recepcionista  
Objetivo: Registrar pagamento da mensalidade.  
Pré-condições: Plano ativo.  
Pós-condições: Pagamento registrado.

---

### UC04 — Verificar Regularidade
Ator Principal: Sistema  
Objetivo: Verificar situação do aluno.  
Pré-condições: Aluno cadastrado.  
Pós-condições: Status atualizado.

---

### UC05 — Validar Acesso na Catraca
Ator Principal: Sistema de Catraca  
Objetivo: Permitir ou bloquear entrada.  
Pré-condições: RFID cadastrado.  
Pós-condições: Acesso validado.

---

### UC06 — Agendar Aula
Ator Principal: Aluno  
Objetivo: Reservar vaga em aula.  
Pré-condições: Aluno ativo.  
Pós-condições: Aula agendada.

---

### UC07 — Cancelar Agendamento
Ator Principal: Aluno  
Objetivo: Cancelar reserva de aula.  
Pré-condições: Agendamento existente.  
Pós-condições: Reserva removida.

---

### UC08 — Realizar Login
Ator Principal: Usuário  
Objetivo: Autenticar acesso ao sistema.  
Pré-condições: Usuário cadastrado.  
Pós-condições: Acesso liberado.

---

### UC09 — Gerar Relatórios
Ator Principal: Administrador  
Objetivo: Emitir relatórios gerenciais.  
Pré-condições: Dados disponíveis.  
Pós-condições: Relatório gerado.

---

### UC10 — Bloquear Aluno
Ator Principal: Sistema  
Objetivo: Bloquear aluno inadimplente.  
Pré-condições: Pagamento em atraso.  
Pós-condições: Acesso bloqueado.

---

### UC11 — Renovar Plano
Ator Principal: Recepcionista  
Objetivo: Renovar plano do aluno.  
Pré-condições: Plano existente.  
Pós-condições: Novo período ativo.

---

### UC12 — Notificar Vencimento
Ator Principal: Sistema  
Objetivo: Avisar sobre vencimento de mensalidade.  
Pré-condições: Data próxima do vencimento.  
Pós-condições: Notificação enviada.

---

### UC13 — Validar CPF
Ator Principal: Sistema  
Objetivo: Validar CPF do aluno.  
Pré-condições: CPF informado.  
Pós-condições: CPF validado ou rejeitado.

---

### UC14 — Gerenciar Planos
Ator Principal: Administrador  
Objetivo: Criar, editar ou remover planos.  
Pré-condições: Acesso administrativo.  
Pós-condições: Plano atualizado.

---

### UC15 — Gerenciar Professores
Ator Principal: Administrador  
Objetivo: Cadastrar ou editar professores.  
Pré-condições: Acesso administrativo.  
Pós-condições: Dados atualizados.

---

### UC16 — Criar Aula
Ator Principal: Administrador  
Objetivo: Cadastrar nova aula.  
Pré-condições: Professor disponível.  
Pós-condições: Aula criada.

---

### UC17 — Excluir Aula
Ator Principal: Administrador  
Objetivo: Remover aula do sistema.  
Pré-condições: Aula existente.  
Pós-condições: Aula removida.

---

### UC18 — Listar Inadimplentes
Ator Principal: Administrador  
Objetivo: Visualizar alunos em atraso.  
Pré-condições: Dados atualizados.  
Pós-condições: Lista exibida.

---

### UC19 — Consultar Histórico de Pagamentos
Ator Principal: Recepcionista  
Objetivo: Visualizar histórico de pagamentos.  
Pré-condições: Aluno cadastrado.  
Pós-condições: Histórico exibido.

---

### UC20 — Integração com Catraca
Ator Principal: Sistema  
Objetivo: Integrar com hardware de acesso.  
Pré-condições: Sistema conectado.  
Pós-condições: Comunicação estabelecida.

---
## Diagramas de Caso de Uso

Nesta seção apresentamos os diagramas de caso de uso do sistema **FitPass Gym Management**.  
Os diagramas representam visualmente as interações entre os atores (Recepcionista, Aluno, Instrutor e Gerente) e os casos de uso principais do sistema, permitindo compreender rapidamente quais funcionalidades estão disponíveis para cada perfil de usuário.

Para facilitar a leitura, os casos de uso foram agrupados em cinco diagramas principais, cada um contemplando um conjunto de funcionalidades relacionadas:

1. **Gestão de Alunos - FitPass:** Cadastro e atualização de dados, incluindo validação de CPF.

<img width="424" height="334" alt="DUC_01_luisfelipecoelho_pollyanacaso (1)" src="https://github.com/user-attachments/assets/60eb5f2b-9c81-414c-ba39-bc5d967b9bee" />

2. **Gestão de Planos e Pagamentos:** Registro de pagamentos, verificação de regularidade e bloqueio de inadimplência.

<img width="759" height="487" alt="DUC_02_luisfelipecoelho_pollyanacaso" src="https://github.com/user-attachments/assets/fff56186-0b68-413c-9d61-08bb1a56bd6a" />

3. **Controle de Acesso:** Criação, edição, ativação e desativação de planos.

<img width="759" height="487" alt="DUC_02_luisfelipecoelho_pollyanacaso" src="https://github.com/user-attachments/assets/093b8d7a-b964-4351-af18-bc26429f13c5" />

4. **Gestão de Aulas:** Reservas de aulas, cancelamentos, registro de presença e consultas de horários.

<img width="379" height="405" alt="DUC_04_luisfelipecoelho_pollyanacaso" src="https://github.com/user-attachments/assets/fb665ff7-0c06-403d-afbb-0297b056c7a9" />

5. **Avaliações, Notificações e Relatórios:** Envio de confirmações, notificações de vencimento e avaliação, além de consulta de histórico de acessos e ocupação das aulas.

<img width="566" height="724" alt="DUC_05_luisfelipecoelho_pollyanacaso (1)" src="https://github.com/user-attachments/assets/72f7af10-061a-4244-b833-de2870fe570d" />

Cada diagrama foi elaborado para ilustrar as funcionalidades de forma clara, destacando os atores envolvidos, os fluxos principais e as relações entre os casos de uso.

