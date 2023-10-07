# Cancelar Consulta

### PROPOSTA DE VALOR

| Como um      | Eu quero                | Então             |
| ------------ | ----------------------- | ----------------- |
| Profissional | Cancelar minha consulta | Remover da agenda |

### CRITÉRIOS DE ACEITAÇÃO

* Usuário deve selecionar um motivo para cancelar a consulta

### IMAGENS

<div>

<figure><img src="../../../.gitbook/assets/Agenda (1).png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/Cancelar consulta - Modal (1).png" alt=""><figcaption></figcaption></figure>

</div>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

1. Usuário clica em Reagendar
2. Usuário clica em cancelar consulta
3. Usuário seleciona \<motivo-do-cancelamento>
   1. Caso o \<motivo-do-cancelamento> esteja selecionado
      1. Usuário pode prosseguir
   2. Caso o \<motivo-do-cancelamento> esteja vazio
      1. Mensagem de alerta (1);
      2. Botão `Confirmar cancelamento` fica desabilitado
4. Usuário clica em Confirmar cancelamento
   1. Sistema remove agendamento da agenda do paciente e do profissional
      1. Sistema envia notificação para o profissional
5. Fim do fluxo

**Pós-condição:**

1. Usuário cancela a consulta

**Mensagens**:

1. mensagem (1): "Informe um motivo para o cancelamento!"
{% endhint %}

### CENÁRIOS

```gherkin
```
