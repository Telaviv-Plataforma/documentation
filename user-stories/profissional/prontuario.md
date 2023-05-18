# Prontuario

### PROPOSTA DE VALOR

| Como um      | Eu quero                     | Então                           |
| ------------ | ---------------------------- | ------------------------------- |
| Profissional | Definir os dados da consulta | Salvar no protuario do paciente |

### CRITÉRIOS DE ACEITAÇÃO

* Sistema deve exibir prontuario do proximo paciente
* Profissional deve informar dados da consulta

### IMAGENS

<figure><img src="../../.gitbook/assets/Prontuário (1).png" alt=""><figcaption></figcaption></figure>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

1. Usuário acessa área do prontuario
   1. Caso não tenha dado o horario da consulta
      1. Botão salvar fica desabilitado
   2. Caso tenha dado o horario da consulta
      1. Usuário pode prosseguir
2. Usuário registra o \<prontuario>
   1. Caso \<campos> obrigatórios estejam vazios
      1. Botão salvar fica desabilitado
   2. Caso \<campos> obrigatorios estejam preenchidos
      1. Usuário pode prosseguir
3. Usuário clica em Salvar
   1. Sistema salva informações no prontuario do usuário
4. Fim do fluxo

**Pós-condição:**

1. Usuário define informações no prontuario do paciente

**Mensagens**:

1. mensagem (1): "Escolha ao menos um dia!"
2. mensagem (2): "Código inválido!"
{% endhint %}

### CENÁRIOS

```gherkin
```
