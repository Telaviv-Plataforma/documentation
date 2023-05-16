# Novo membro

### PROPOSTA DE VALOR

| Como um | Eu quero                 | Então                       |
| ------- | ------------------------ | --------------------------- |
| Usuário | Registrar um novo membro | agendar consultas para eles |

### CRITÉRIOS DE ACEITAÇÃO

* Ter o plano familia assinado
* O usuário deve informar os campos:
  * Se o membro é menor de idade
  * Nome Completo
  * CPF (Opcional para menores de idade)
  * E-mail
  * Telefone
  * CEP
  * Endereço

### IMAGENS

<div>

<figure><img src="../../.gitbook/assets/Meu perfil.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Cadastrar membro.png" alt=""><figcaption></figcaption></figure>

</div>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário paciente
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

* Usuário acessa a área do perfil
  1. Sistema exibe lista de membros
* Usuário clica em `Novo membro`
  1. Sistema exibe a página de Registro de membro
* Usuário insere \<parametros>
  1. Caso o \<parametro> não seja válido
     1. Mensagem de alerta (1);
     2. Botão `Novo membro` fica desabilitado
  2. Caso o \<parametro> seja válido
     1. Usuário pode prosseguir
* Usuário clica em `Novo membro`
  1. Sistema salva novo membro
* Fim do fluxo.

**Pós-condição:**

1. Registrar nova conta

**Mensagens**:

1. mensagem (1): "Dados invalidos!"
2. mensagem (2): "Você deve aceitar os termos de uso!"
3. mensagem (3): "Senha invalida!"
4. mensagem (4): "Selecione uma das assinaturas!"
5. mensagem (5): "Dados de pagamento invalidos!"
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
