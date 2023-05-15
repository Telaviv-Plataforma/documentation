# Nova Consulta

### PROPOSTA DE VALOR

| Como um  | Eu quero             | Então                                     |
| -------- | -------------------- | ----------------------------------------- |
| Paciente | Agendar uma consulta | Salvar consulta na agenda do profissional |

### CRITÉRIOS DE ACEITAÇÃO

* Usuário deve selecionar um tipo de profissional
* Usuário deve selecionar um horario para o agendamento
* Sistema deve mostrar todos os profissionais disponiveis para a o horario e area selecionados

### IMAGENS

<div>

<figure><img src="../../.gitbook/assets/Agendar (selecionar profissional).png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Selecione um horario.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Selecione um profissional.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/Selecione um profissional (1).png" alt=""><figcaption></figcaption></figure>

</div>

### HISTÓRIA DO USUÁRIO

{% hint style="info" %}
**Atores**: Usuário
{% endhint %}

{% hint style="warning" %}
**Fluxo principal:**

1. Usuário clica em Nova consulta
   1. Sistema exibe lista de áreas médicas
2. Usuário seleciona uma das áreas
3. Usuário insere \<dados-do-agendamento>
   1. Caso os \<dados-do-agendamento> sejam válidos
      1. Usuário pode prosseguir
   2. Caso os \<dados-do-agendamento> sejam inválidos
      1. Mensagem de alerta (1);
      2. Botão `Agendar` fica desabilitado
4. Usuário clica em Agendar
   1. Sistema exibe lista de profissionais disponiveis
5. Usuário seleciona um dos profissionais
   1. Sistema exibe resumo do agendamento
      1. Caso o usuário clique em Confirmar consulta
         1. Sistema salva consulta na agenda do paciente e do profissional
      2. Caso o usuário clique em Cancelar
         1. Angendamento é cancelado
6. Fim do fluxo

**Pós-condição:**

1. Usuário registra nova consulta

**Mensagens**:

1. mensagem (1): "Informe uma data valida!"
{% endhint %}

### CENÁRIOS

```gherkin
@New_Schedule
Feature: New medical appointment
    In order to I can register a new appointment
    As a patient I want to register a New medical appointment

    Scenario: Register a New medical appointment
        Given I visit "/new-appointment" page
        When I select a <medial-area>
        And I enter <schedule> in the schedules fields
        And I click "Schedule"
        And I select a <professional>
        And the system display the schedule resume
        Then I click in confirm
        And the system save the schedule on the patient and professional agenda
```
