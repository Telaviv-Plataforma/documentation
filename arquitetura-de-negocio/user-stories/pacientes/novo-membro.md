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

<figure><img src="../../../.gitbook/assets/Meu perfil.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/Cadastrar membro.png" alt=""><figcaption></figcaption></figure>

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
* Usuário insere \<parâmetros>
  1. Caso o \<parâmetro> não seja válido
     1. Mensagem de alerta (1);
     2. Botão `Novo membro` fica desabilitado
  2. Caso o \<parâmetro> seja válido
     1. Usuário pode prosseguir
* Usuário clica em `Novo membro`
  1. Sistema salva novo membro
* Fim do fluxo.

**Pós-condição:**

1. Registrar nova conta

**Mensagens**:

1. mensagem (1): "Dados inválidos!"
{% endhint %}

### CENÁRIOS

```gherkin
```
