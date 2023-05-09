# Nova Consulta

### PROPOSTA DE VALOR

| Como um  | Eu quero             | Então                                     |
| -------- | -------------------- | ----------------------------------------- |
| Paciente | Agendar uma consulta | Salvar consulta na agenda do profissional |

### CRITÉRIOS DE ACEITAÇÃO

* Usuário deve selecionar um tipo de profissional
* Usuário deve selecionar um horario para o agendamento
* Sistema deve mostrar todos os profissionais disponiveis para a o horario e area selecionados

### IMAGENS

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

1. Usuário clica em Nova consulta
   1. Sistema exibe lista de áreas médicas
2. Usuário seleciona uma das áreas
3. Usuário insere \<dados-do-agendamento>
   1. Caso os \<dados-do-agendamento> sejam válidos
      1. Usuário pode prosseguir
   2. Caso os \<dados-do-agendamento> sejam inválidos
      1. Mensagem de alerta (2);
      2. Botão `Agendar` fica desabilitado
4. Usuário clica em Agendar
   1. Sistema exibe lista de profissionais disponiveis
5. Usuário seleciona um dos profissionais
   1. Sistema exibe resumo do agendamento
      1. Caso o usuário clique em Confirmar consulta
         1. Sistema salva consulta na agenda do paciente e do profissional
      2. Caso o usuário clique em Cancelar
         1. Angendamento é cancelado
6. Fim do fluxo

**Pós-condição:**

1. Usuário cadastra nova senha

**Mensagens**:

1. mensagem (1): "E-mail inválido!"
2. mensagem (2): "Código inválido!"
3. mensagem (3): "Senha inválida!"
{% endhint %}

### CENÁRIOS

```gherkin
@Recovery_account
Feature: Receive code for account recovery
    In order to I can not access my account
    As a registered user I want recovery my account

    Scenario: Registered e-mail
        Given I visit "/login" page
        And I click "Recovery account"
        When I enter <email> in the e-mail field
        And I click "Confimed"
        And system return e-mail registered <true>
        Then I see a success <message>
        And I recive an e-mail with <code> to recovery my account

    Scenario: Unregistered email
        Given I visit "/login" page
        And I click "Recovery account"
        When I enter <email> in the e-mail field
        And I click "Confimed"
        And system return e-mail registered <false>
        Then I see a warning <message>
        
    Scenario: Inform valid code
        Given I visit "/confirm-code" page
        When I enter <code> in the code field
        And I click "Confimed"
        Then I see a success <message>
        And I can define a new password

    Scenario: Inform invalid code
        Given I visit "/confirm-code" page
        When I enter a invalid <code> in the code field
        Then I click "Confirm" button is disabled
        And I see a warning message

Feature: Change password
    In order to I can not access my account
    As a registered user I want to change my password

    Scenario: Change password with valid new password
        Given I enter  <password> in the "Password" field
        And I enter  <password> in the "Confirme Password" field
        When I click "Confirme" button
        Then I see a success <message>
        And system return to "/login" page

    Scenario: Change password with invalid new password
        Given I enter  <password> in the "Password" field
        And I enter  <password> in the "Confirme Password" field
        When I click "Confirme" button
        Then I see a warning <message> 
```
