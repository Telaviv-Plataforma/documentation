# Recuperar acesso

### PROPOSTA DE VALOR

| Como um       | Eu quero                      | Então            |
| ------------- | ----------------------------- | ---------------- |
| Administrador | recuperar acesso da aplicação | Recuperar acesso |

### CRITÉRIOS DE ACEITAÇÃO

* Usuário deve possuir uma Conta registrada
* Usuário deve informar o e-mail cadastrado
  * Sistema deve enviar um e-mail para registrar nova senha

### IMAGENS

<figure><img src="../../../.gitbook/assets/Recuperar acesso - 1 (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Recuperar acesso - 2 (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Recuperar acesso - 3 (2).png" alt=""><figcaption></figcaption></figure>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

1. Usuário clica em `Esqueceu sua senha?`
   1. Sistema exibe página de recuperação de acesso
2. Usuário preenche o campo login com `E-mail` cadastrado
   1. Caso o \<e-mail> seja inválido
      1. Mensagem de alerta (1);
      2. Botão `Enviar código` fica desabilitado
   2. Caso o \<e-mail> seja válido
      1. Usuário pode prosseguir
3. Usuário clica em `Enviar código`
   1. Sistema envia código de recuperação para e-mail
   2. Sistema exibe página de confirmação de código
4. O usuário informa o código de confirmação
   1. Caso o \<código> seja válido
      1. Usuário pode prosseguir
   2. Caso o \<código> seja inválido
      1. Mensagem de alerta (2);
      2. Botão `Confirmar código` fica desabilitado
   3. Caso o usuário não tenha recebido o código
      1. Usuário clica em `Reenviar código`
         1. Sistema reenvia código para o e-mail
         2. Etapa 4
5. Usuário clica em `Confirmar código`
   1. Sistema exibe página de Definição de senha
6. Usuário preenche o campo Nova senha com `Senha`
7. Usuário preenche o campo Confirme nova senha com `Senha`
   1. Caso a \<senha> seja válida
      1. Usuário pode prosseguir
   2. Caso a \<senha> seja inválida
      1. Mensagem de alerta (3);
      2. Botão `Avançar` fica desabilitado
8. Usuário clica em `Avançar`
   1. Sistema exibe página de Sign In
9. Fim do fluxo

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
