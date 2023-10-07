# Avaliar Consulta

### PROPOSTA DE VALOR

| Como um  | Eu quero               | Então              |
| -------- | ---------------------- | ------------------ |
| Paciente | Finalizar uma consulta | Avaliar a consulta |

### CRITÉRIOS DE ACEITAÇÃO

* Usuário deve ter concluido a consulta

### IMAGENS

<div>

<figure><img src="../../../.gitbook/assets/Minha agenda.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/Confirmar consulta.png" alt=""><figcaption></figcaption></figure>

</div>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

1. Usuário clica em Confirmar consulta
2. Usuário seleciona se o profissional compareceu
   1. Se não compareceu
      1. Usuário pode prosseguir
   2. Se compareceu
      1. Sistema habilita as estrelas de avaliação
3. Usuário avalia o profissional utilizando as estrelas
4. Usuário clica em confirmar
   1. Sistema registra avaliação do profissional
5. Fim do fluxo

**Pós-condição:**

1. Usuário avalia o profissional
{% endhint %}

### CENÁRIOS

```gherkin
```
