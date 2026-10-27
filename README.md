# YourPetHealth — Compliance, Quality Assurance & Tests (Sprint 4)

Plataforma que centraliza a rotina de clínicas veterinárias e de responsáveis por pets: cadastro de pets, agendamento de consultas, atendimento veterinário, histórico clínico e acompanhamento da saúde dos animais.

## Links da entrega

| Item | Link |
|---|---|
| Projeto no Azure DevOps (backlog) | https://dev.azure.com/RM562850/Sprint%2004 |
| Plano de testes manuais (Azure Test Plans) | https://dev.azure.com/RM562850/Sprint%2004/_testPlans/define?planId=188 |
| Consulta de rastreabilidade (histórias × casos de teste) | https://dev.azure.com/RM562850/Sprint%2004/_queries/query/4427b07c-9761-4eed-9058-c382b3825a14/ |
| Vídeo dos testes automatizados | **PREENCHER** |
| API testada | https://yourpethealth-java.onrender.com |

## Conteúdo do repositório

| Arquivo | O que é |
|---|---|
| `README.md` | Este documento: links da entrega, release plan, plano de testes e resultados |
| `YourPetHealth.postman_collection.json` | Coleção do Postman com os testes automatizados da API |
| `YourPetHealth-UI.side` | Projeto do Selenium IDE com os testes automatizados das telas do aplicativo |

---

## Backlog e release plan

O backlog está organizado em 4 épicos, 8 features e 19 histórias de usuário (Product Backlog Items), todas escritas do ponto de vista de quem usa o produto — **Como [perfil], quero [ação], para [benefício]** — com critérios de aceite em cenários **Dado / Quando / Então**. O trabalho técnico de API, aplicativo e testes está nas tarefas de cada história.

| Sprint | Histórias | Pontos |
|---|---|---|
| Sprint 1 | US01, US02, US03, US04, US05, US06 | 26 |
| Sprint 2 | US07, US08, US09, US10, US11 | 28 |
| Sprint 3 | US12, US13, US14, US15, US16 | 24 |
| Sprint 4 (atual) | US17, US18, US19 | 26 |

---

## Parte A — Testes manuais de sistema

São **40 casos de teste**, um para cada cenário de aceite das histórias entregues. Estão no **Azure Test Plans**, no plano **Plano de Testes - Sprint 4**, e cada caso está ligado pelo link **Tested By** à história que valida. É esse link que conecta cada teste ao release plan.

Cada caso é escrito em passos, no formato do Test Plans:

- **Passo 1 (preparação):** objetivo do teste, história e cenário de aceite validados, pré-condições e dados de entrada, com valores fixos
- **Passos seguintes:** a ação executada e o resultado esperado, que são os dados de saída do teste

### Matriz de rastreabilidade

| História | Sprint | Casos de teste |
|---|---|---|
| US01 - Como novo usuário, quero criar minha conta | 1 | CT01.1, CT01.2, CT01.3, CT01.4 |
| US02 - Como usuário, quero entrar na plataforma e continuar conectado | 1 | CT02.1, CT02.2, CT02.3 |
| US03 - Como usuário, quero ver meus dados e sair da conta | 1 | CT03.1, CT03.2 |
| US04 - Como responsável, quero cadastrar meu pet | 1 | CT04.1, CT04.2 |
| US05 - Como responsável, quero consultar meus pets | 1 | CT05.1, CT05.2 |
| US06 - Como responsável, quero atualizar os dados do meu pet | 1 | CT06.1, CT06.2 |
| US07 - Como responsável, quero agendar uma consulta para meu pet | 2 | CT07.1, CT07.2, CT07.3, CT07.4 |
| US08 - Como responsável, quero acompanhar as consultas dos meus pets | 2 | CT08.1, CT08.2, CT08.3 |
| US09 - Como responsável, quero remarcar uma consulta | 2 | CT09.1, CT09.2 |
| US10 - Como responsável, quero cancelar uma consulta | 2 | CT10.1, CT10.2 |
| US11 - Como responsável, quero excluir uma consulta marcada por engano | 2 | CT11.1, CT11.2 |
| US12 - Como veterinário, quero ver minha agenda de atendimentos | 3 | CT12.1, CT12.2 |
| US13 - Como veterinário, quero registrar o atendimento e concluir a consulta | 3 | CT13.1, CT13.2 |
| US14 - Como responsável, quero consultar o histórico clínico do meu pet | 3 | CT14.1, CT14.2 |
| US15 - Como responsável, quero ter meus dados protegidos de outros usuários | 3 | CT15.1, CT15.2 |
| US16 - Como responsável, quero remover um pet do meu cadastro | 3 | CT16.1, CT16.2 |
| US17 - Como responsável, quero ver o resumo e os alertas dos meus pets na tela inicial | 4 | CT17.1, CT17.2 |
| US18 - Como responsável, quero saber se o acompanhamento de saúde do meu pet está em dia | 4 | Em desenvolvimento na sprint atual |
| US19 - Como responsável, quero ser avisado quando meu pet correr risco de ficar sem acompanhamento | 4 | Em desenvolvimento na sprint atual |

US18 e US19 estão em desenvolvimento na Sprint 4. Os casos de teste delas serão escritos a partir dos cenários de aceite quando a implementação for entregue, seguindo a regra de testar o que já foi realizado.

### Massa de dados controlada

**Usuários**

| Id | Nome | Acesso | Perfil |
|---|---|---|---|
| U1 | Ana Tutora Teste | tutor.teste@yourpet.com / Senha@123 | Responsável |
| U2 | Bruno Vet Teste | vet.teste@yourpet.com / Senha@123 | Veterinário · CRMV SP-99999 · Clínica Geral |
| U3 | Carla Tutora Teste | tutora2.teste@yourpet.com / Senha@123 | Responsável |
| U4 | Diego Tutor Teste | tutor3.teste@yourpet.com / Senha@123 | Responsável, sem pets |

**Pets**

| Id | Pet | Dados | Responsável |
|---|---|---|---|
| P1 | Thor | Golden Retriever · 7 anos · 41.2 kg · Macho | Ana |
| P2 | Mel | Poodle · 4 anos · 6.5 kg · Fêmea | Ana |
| P3 | Fred | SRD · 2 anos · 10.0 kg · Macho | Ana — usado no teste de remoção |
| P4 | Pipoca | Beagle · 3 anos · 12.0 kg · Fêmea | Carla |

**Consultas** (todas com o veterinário Bruno)

| Id | Pet | Tipo e descrição | Data | Uso nos testes |
|---|---|---|---|---|
| C1 | Thor | Rotina · Check-up semestral | 09/11/2026 10:00 | Criada no CT07.1 e concluída no CT13.1 |
| C2 | Mel | Vacinação · Vacina anual | 09/11/2026 14:00 | Remarcada para 10/11/2026 15:00 no CT09.1 |
| C3 | Thor | Retorno · Retorno do check-up | 11/11/2026 11:00 | Cancelada no CT10.1 |
| C4 | Mel | Exame · Exame de sangue | 12/11/2026 09:00 | Excluída no CT11.1 |
| C5 | Mel | Rotina · Avaliação geral | 09/11/2026 08:00 | Agenda do veterinário e conclusão recusada |

**Ordem de execução:** numérica, de CT01.1 a CT17.2. A única exceção é o CT08.2, que usa a consulta cancelada no CT10.1. As datas foram escolhidas para execução até 08/11/2026; depois disso, avance todas as datas uma semana, mantendo os mesmos dias da semana.

---

## Parte B — Testes automatizados

São duas automações, e cada teste leva o código do caso de teste manual que automatiza:

- **B1. API, com Postman:** testes de integração na API Java
- **B2. Telas do aplicativo, com Selenium IDE:** testes de interface com a ferramenta de Record & Playback, no aplicativo executado na versão web

### B1. API — Postman

A coleção `YourPetHealth.postman_collection.json` tem 21 requisições e 48 asserções, executadas em sequência pelo Collection Runner. Cada requisição verifica o status HTTP e o conteúdo da resposta, incluindo o formato padronizado de erro da API.

#### Como executar

1. No Postman, clique em **Import** e selecione `YourPetHealth.postman_collection.json`
2. Abra a URL da API no navegador e aguarde a resposta — o servidor gratuito do Render hiberna e leva até um minuto para acordar
3. Clique com o botão direito na coleção → **Run collection** → **Run**
4. A execução deve terminar com todas as asserções aprovadas

Cada execução cria usuários novos, com um sufixo numérico no e-mail e um CRMV diferente, para que a coleção possa ser rodada várias vezes sem conflito. Os demais dados são fixos.

#### Casos automatizados

| # | Caso automatizado | Resultado esperado |
|---|---|---|
| 00 | Preparação — API no ar | Resposta sem erro de servidor |
| 01 | CT01.2 — Criar conta de veterinário com CRMV | 201 · perfil VETERINARIO |
| 02 | CT01.4 — Cadastro de veterinário sem CRMV | 409 · CONFLITO |
| 03 | CT01.1 — Criar conta de responsável | 201 · perfil RESPONSAVEL |
| 04 | CT01.3 — Cadastro com e-mail já cadastrado | 409 · CONFLITO |
| 05 | CT02.2 — Entrar com senha incorreta | 401 · NAO_AUTORIZADO |
| 06 | CT02.1 — Entrar com e-mail e senha corretos | 200 · token Bearer |
| 07 | US15 — Acessar os pets sem estar conectado | 401 · NAO_AUTORIZADO |
| 08 | CT04.1 — Cadastrar pet com dados válidos | 201 · dados gravados |
| 09 | CT04.2 — Cadastrar pet com peso inválido | 400 · VALIDACAO no campo peso |
| 10 | CT07.1 — Agendar consulta válida | 201 · AGENDADA |
| 11 | CT07.2 — Agendar com menos de 2 horas de antecedência | 400 · VALIDACAO |
| 12 | CT07.3 — Agendar consulta em um domingo | 400 · VALIDACAO |
| 13 | CT07.4 — Agendar com veterinário ocupado | 409 · CONFLITO |
| 14 | CT16.2 — Remover pet com consulta agendada | 409 · CONFLITO |
| 15 | CT15.1 — Responsável tenta abrir a agenda do veterinário | 403 · ACESSO_NEGADO |
| 16 | Preparação — Agendar a consulta que será cancelada | 201 |
| 17 | CT10.1 — Cancelar consulta agendada | 200 · CANCELADA |
| 18 | CT13.2 — Concluir atendimento com observações curtas | 400 · VALIDACAO |
| 19 | CT13.1 — Concluir atendimento com observações válidas | 200 · REALIZADA |
| 20 | CT14.1 — Ver o histórico com o atendimento concluído | 200 · registro gerado |

#### Defeito encontrado pela automação

Na primeira execução, 47 das 48 asserções passaram. A que falhou foi do teste 11 (CT07.2): a API recusou um agendamento marcado para 1 hora à frente do horário de Brasília tratando a data como já passada, porque o servidor hospedado no Render usa o horário UTC, três horas à frente. Para o usuário, a regra das 2 horas de antecedência fica deslocada em 3 horas: um agendamento feito com 2 a 5 horas de antecedência, no horário de Brasília, é recusado.

- **Correção proposta para a API:** configurar a variável de ambiente `TZ=America/Sao_Paulo` no serviço do Render.
- **Ajuste no teste:** o teste 11 passou a calcular o horário a partir do relógio do próprio servidor (campo `timestamp` da resposta de erro, lido na requisição 00), para validar a regra de antecedência independentemente do fuso do servidor.

### B2. Telas do aplicativo — Selenium IDE

O projeto `YourPetHealth-UI.side` é aberto no **Selenium IDE 4** e tem 6 testes. Os testes navegam pelo aplicativo como um usuário: preenchem campos, tocam nos botões e conferem o que aparece na tela. Cada comando tem um comentário com o passo correspondente do caso de teste manual.

O projeto tem duas suítes:

- **Todos os testes em sequência (uma janela):** executa os 6 testes um depois do outro na mesma janela, pelo teste *00 - Executar os 6 testes em sequência*. É a suíte usada na entrega
- **Testes de interface - YourPetHealth:** os mesmos 6 testes como itens separados. Nesta suíte, o Selenium IDE 4, que ainda é beta, abre uma janela nova para cada teste e às vezes para a execução no terceiro teste, mesmo com os testes passando quando rodados sozinhos. Por isso a entrega usa a suíte em uma janela

#### Como executar

1. Abra https://yourpethealth-java.onrender.com/api/veterinarios no navegador e aguarde a resposta, para acordar a API
2. Na pasta do aplicativo mobile, crie o arquivo `.env` com a linha `EXPO_PUBLIC_API_URL=https://yourpethealth-java.onrender.com`
3. Rode `npm install` e depois `npx expo start --web`. O aplicativo abre em http://localhost:8081
4. No Selenium IDE, clique em **Load Project** e selecione `YourPetHealth-UI.side`
5. Na aba **Suites**, selecione **Todos os testes em sequência (uma janela)** e clique em **Play Suite**

Cada teste começa executando o CT01.1 (comando `run`), que cria uma conta nova com um e-mail diferente a cada execução. Assim, nenhum teste depende de dados criados antes, e a suíte pode ser repetida quantas vezes for preciso. As esperas vão até 30 segundos, porque a API gratuita pode demorar para responder.

#### Casos automatizados

| Teste | O que é verificado na tela |
|---|---|
| CT01.1 — Criar conta de responsável com dados válidos | A conta é criada e o aplicativo abre a tela inicial com "Olá, Ana Tutora Teste" |
| CT02.1 — Entrar com e-mail e senha corretos | O login abre a tela inicial do responsável |
| CT02.2 — Entrar com senha incorreta | Aparece a mensagem "E-mail ou senha inválidos", e o aplicativo continua na tela de login |
| CT04.1 — Cadastrar pet com dados válidos | Thor aparece na lista como "Golden Retriever • 7 anos • 41.2 kg", e o aplicativo avisa que o pet foi cadastrado |
| CT04.2 — Cadastrar pet com peso inválido | Aparece "Peso deve ser maior que 0 e menor que 200", e o pet não é cadastrado |
| CT15.1 — Responsável tenta abrir a agenda do veterinário | Aparece a tela 403 "Acesso negado", sem dados da agenda, e o botão de voltar leva à tela inicial |

No CT04.1, o aviso de sucesso do aplicativo usa a janela de alerta do navegador. Um comando `executeScript` guarda o texto desse aviso antes do clique em salvar, e o teste confere a mensagem sem ficar preso na janela.

---

## Integrantes

| Nome | RM |
|---|---|
| Guilherme Cintra | RM562850 |
| Erick de Faria Gama | RM561951 |
| Matheus Nascimento Corregio | RM563765 |
| Pedro Fonseca de Almeida | RM563466 |
| Daniel Fonseca de Almeida | RM563045 |
