# Prontuário

### PROPOSTA DE VALOR

| Como um      | Eu quero                     | Então                           |
| ------------ | ---------------------------- | ------------------------------- |
| Profissional | Definir os dados da consulta | Salvar no protuário do paciente |

### CRITÉRIOS DE ACEITAÇÃO

* Sistema deve exibir prontuário do próximo paciente
* Profissional deve informar dados da consulta

### IMAGENS

<figure><img src="../../../.gitbook/assets/Prontuário (1).png" alt=""><figcaption></figcaption></figure>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

1. Usuário acessa área do prontuário
   1. Caso não tenha dado o horário da consulta
      1. Botão salvar fica desabilitado
   2. Caso tenha dado o horario da consulta
      1. Usuário pode prosseguir
2. Usuário registra o \<prontuário>
   1. Caso \<campos> obrigatórios estejam vazios
      1. Botão salvar fica desabilitado
   2. Caso \<campos> obrigatórios estejam preenchidos
      1. Usuário pode prosseguir
3. Usuário clica em Salvar
   1. Sistema salva informações no prontuário do usuário
4. Fim do fluxo

**Pós-condição:**

1. Usuário define informações no prontuário do paciente

**Mensagens**:

1. mensagem (1): "Escolha ao menos um dia!"
2. mensagem (2): "Código inválido!"
{% endhint %}

### CENÁRIOS

```gherkin
```
