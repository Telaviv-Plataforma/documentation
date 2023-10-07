# Criar conta

### PROPOSTA DE VALOR

| Como um | Eu quero        | Então             |
| ------- | --------------- | ----------------- |
| Usuário | ser um Paciente | Criar minha conta |

### CRITÉRIOS DE ACEITAÇÃO

* O usuário deve informar os campos:
  * Nome Completo
  * CPF ou CNPJ
  * E-mail
  * Telefone
  * Senha
  * Confirmação de senha
* Usuário confirmar os termos de uso

### IMAGENS

<div>

<figure><img src="../../../.gitbook/assets/iPhone 14 - 6.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/iPhone 14 - 7.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/Primeiro acesso.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/Pagamento (2).png" alt=""><figcaption></figcaption></figure>

</div>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário paciente
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

* Usuário acessa a aplicação
  1. Sistema exibe página de Sign In
* Usuário clica em `Cadastrar`
  1. Sistema exibe a página de Registro de conta 1
* Usuário insere \<nome-completo>, \<cpf> e outros parametros
  1. Caso o \<parametro> não seja válido
     1. Mensagem de alerta (1);
     2. Botão `Continuar` fica desabilitado
  2. Caso o \<parâmetro> seja válido
     1. Usuário pode prosseguir
* Usuário confirma os \<termos>
  1. Caso os \<termos> não sejam confirmados
     1. Mensagem de alerta (2);
        1. Botão `Continuar` fica desabilitado
  2. Caso os \<termos> sejam confirmados
     1. Usuário pode prosseguir
* Usuário clica em `Continuar`
  1. Sistema exibe segunda etapa do cadastro
* Usuário insere uma \<senha> e \<confirmar-senha>
  1. Caso a \<senha> seja válida
     1. Usuário pode prosseguir
  2. Caso a \<senha> seja inválida
     1. Mensagem de alerta (3);
     2. Botão `Registrar` fica desabilitado
* Usuário clica em `Registrar`
  1. Sistema registra a conta
  2. Sistema exibe terceira etapa do cadastro
* Usuário seleciona uma \<assinatura>
  * Caso o usuário selecione
    1. Usuário pode prosseguir
  * Caso o usuário não selecione
    1. Mensagem de alerta (4);
    2. Botão `Continuar` fica desabilitado
* Usuário clica em Continuar
  * Sistema exibe tela de pagamento
* Usuário insere \<dados-de-pagamento>
  1. Caso os \<dados-de-pagamento> sejam válidos
     1. Usuário pode prosseguir
  2. Caso os \<dados-de-pagamento> sejam inválidos
     1. Mensagem de alerta (5);
     2. Botão `Continuar` fica desabilitado
* Usuário clica em `Continuar`
  * Caso o \<pagamento> não seja confirmado
    1. Mensagem de alerta (6);
  * Caso o \<pagamento> seja confirmado
    1. Usuário pode prosseguir
* Fim do fluxo.

**Pós-condição:**

1. Registrar nova conta

**Mensagens**:

1. mensagem (1): "Dados inválidos!"
2. mensagem (2): "Você deve aceitar os termos de uso!"
3. mensagem (3): "Senha inválida!"
4. mensagem (4): "Selecione uma das assinaturas!"
5. mensagem (5): "Dados de pagamento inválidos!"
6. mensagem (6): "Pagamento não aprovado!"
{% endhint %}

### CENÁRIOS

```gherkin
@Create_account
Feature: Create Account
In order to I don't have an account
As a user I want to create my account

Background:
 Given I acess the Sigup Page
 When I selected "Create account"
 Then system display the Register account page
 
Scenario: Create account with valid parameter
 When I fill a valid <Parameter>
 And I click in "Continuar"
 And the <policy> in checked
 Then I should see the next step

Scenario: Create account with invalid parameter
 When I fill the invalid <parameters>
 Then the system disable the "Continuar" button
 And I should see a warning message
 
Scenario: Create account with no policy checked
 When I fill <Parameter>
 And I click in "Continuar"
 And the <policy> in unchecked
 Then I should see a warning message
 
Scenario: Payment approved
 When I fill a valid <payment-data>
 And I click in "Continuar"
 And the <payment> is approved
 Then the system register my account
 
Scenario: Payment refused
 When I fill a valid <payment-data>
 And I click in "Continuar"
 And the <payment> is refused
 Then I should see a warning message
```
