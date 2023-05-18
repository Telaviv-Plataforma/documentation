# Criar conta

### PROPOSTA DE VALOR

| Como um | Eu quero            | Então             |
| ------- | ------------------- | ----------------- |
| Usuário | ser um Profissional | Criar minha conta |

### CRITÉRIOS DE ACEITAÇÃO

* O usuário deve informar os campos:
  * Nome Completo
  * CPF ou CNPJ
  * E-mail
  * Telefone
  * Senha
  * Confirmação de senha
  * Especialidade
  * Organização de ensino
  * Ano de formação
  * Se possui experiência
  * CRM
* Usuário confirmar os termos de uso
* O usuário deve fazer o upload do:
  * Currículo
  * Foto de um documento
  * Comprovante do CRM

### IMAGENS

<figure><img src="../../.gitbook/assets/Desktop - 4.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Desktop - 6.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Desktop - 8.png" alt=""><figcaption></figcaption></figure>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário profissional
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

* Usuário acessa a aplicação
  1. Sistema exibe página de Sign In
* Usuário clica em `Cadastrar`
  1. Sistema exibe a página de Registro de conta 1
* Usuário insere \<parâmetros>
  1. Caso o \<parâmetro> não seja válido
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
     2. Botão `Continuar` fica desabilitado
* Usuário clica em `Continuar`
  1. Sistema exibe terceira etapa do cadastro
* Usuário faz upload de \<documentos>
  * Caso o usuário faça um upload válido
    1. Usuário pode prosseguir
  * Caso o usuário não faça um upload válido
    1. Mensagem de alerta (4);
    2. Botão `Enviar e finalizar` fica desabilitado
* Usuário clica em Enviar e finalizar
  * Sistema envia solicitação para o backoffice analisar
* Fim do fluxo.

**Pós-condição:**

1. Registrar nova conta

**Mensagens**:

1. mensagem (1): "Dados inválidos!"
2. mensagem (2): "Você deve aceitar os termos de uso!"
3. mensagem (3): "Senha inválida!"
4. mensagem (4): "Formato inválido!"
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
```
