# Meu prontuário

### PROPOSTA DE VALOR

| Como um | Eu quero                           | Então                    |
| ------- | ---------------------------------- | ------------------------ |
| Usuário | Alterar minhas informações médicas | exibir no meu prontuário |

### CRITÉRIOS DE ACEITAÇÃO

* Informar se tem
  * Diabetes
  * Alergias
  * Doenças no coração
  * Doenças
  * Vícios
  * Gestante
  * Outros

### IMAGENS

<div>

<figure><img src="../../.gitbook/assets/Meu perfil.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Prontuário.png" alt=""><figcaption></figcaption></figure>

</div>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário paciente
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

* Usuário acessa a área do perfil
  1. Sistema exibe lista de membros
* Usuário clica em um dos membros
  1. Sistema exibe a página de prontuário
* Usuário insere \<parâmetros>
  1. Caso o \<parâmetro> não seja válido
     1. Mensagem de alerta (1);
     2. Botão `Novo membro` fica desabilitado
  2. Caso o \<parâmetro> seja válido
     1. Usuário pode prosseguir
* Fim do fluxo.

**Pós-condição:**

1. Registrar nova conta

**Mensagens**:

1. mensagem (1): "Dados inválidos!"
{% endhint %}

### CENÁRIOS

```gherkin
```
