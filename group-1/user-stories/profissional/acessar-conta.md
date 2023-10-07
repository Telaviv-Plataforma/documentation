# Acessar conta

### PROPOSTA DE VALOR

| Como um      | Eu quero         | Então               |
| ------------ | ---------------- | ------------------- |
| Profissional | Usar a aplicação | Acessar a aplicação |

### CRITÉRIOS DE ACEITAÇÃO

* Usuário deve possuir uma conta registrada e aprovada pelo backoffice
* Usuário inserir uma senha válida
* Usuário inserir um e-mail válido
* Caso o 2FA esteja ativo, usuário deve inserir o código de validação

### IMAGENS

<figure><img src="../../../.gitbook/assets/Desktop - 7.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Autenticação.png" alt=""><figcaption></figcaption></figure>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário profissional
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

1. Usuário acessa a aplicação
   1. Sistema exibe página de Sign In
2. Usuário insere o \<e-mail>
   1. Caso o \<e-mail> seja válido
      1. Usuário pode prosseguir
   2. Caso o \<e-mail> seja inválido
      1. Mensagem de alerta (1);
      2. Botão `Entrar` fica desabilitado
3. Usuário insere a \<senha>
   1. Caso a \<senha> seja válida
      1. Usuário pode prosseguir
   2. Caso a \<senha> seja inválida
      1. Mensagem de alerta (2);
      2. Botão `Entrar` fica desabilitado
4. Usuário clica em `Entrar`
   1. Caso o usuário esteja com o 2FA ativo
      1. Sistema exibe tela de autenticação de código
         1. Usuário informa \<código> de autenticação
            1. Caso o \<código> seja válido
               1. Usuário pode prosseguir
            2. Caso o \<código> seja inválido
               1. Mensagem de alerta (3);
               2. Botão `Continuar` fica desabilitado
         2. Usuário clica em `Continuar`
5. Fim do Fluxo

**Pós-condição:**

1. Usuário pode acessar a aplicação

**Mensagens**:

1. mensagem (1): "E-mail inválido!"
2. mensagem (2): "Senha inválida!"
{% endhint %}

### CENÁRIOS

```gherkin
@Sign_ing
Feature: Sign in account
In order to I have a account
As a user I want to Sigin with my password

Scenario: Sign in with a valid information
 When I fill a valid <email> & <Password>
 And I click in "Sign in"
 Then system authenticate my user
 And I should see home page
 
Scenario: Sign in with a invalid information
 When I fill a invalid <email> & <Password>
 And I click in "Sign in"
 Then should see a warning message
 
Scenario: Sign in with a valid authentication code
 Given I have the 2FA active
 When I fill a valid <email> & <Password>
 And I click in "Sign in"
 And I fill a valid <code>
 And I click in "Continue"
 Then system authenticate my user
 And I should see home page
 
Scenario: Sign in with a invalid authentication code
 Given I have the 2FA active
 When I fill a valid <email> & <Password>
 And I click in "Sign in"
 And I fill a invalid <code>
 And I click in "Continue"
 Then should see a warning message
```
