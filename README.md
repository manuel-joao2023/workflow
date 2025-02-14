# Documentação do Sistema de Workflow

## Introdução
O sistema de Workflow tem como objetivo gerenciar processos automatizados, garantindo que as etapas de um fluxo de trabalho sejam executadas de forma ordenada e eficiente. Ele permite definir tipos de workflow, etapas, sequências, execuções e históricos, proporcionando rastreabilidade e controle sobre cada processo.

O sistema é baseado em um conjunto de entidades interconectadas, permitindo que os workflows sejam configuráveis e adaptáveis a diferentes cenários organizacionais.

## Status
- **Anulado**: 0
- **Em curso**: 1
- **Concluído**: 2

## Entidades do Sistema

### Workflow
- **Id**: Identificador único do workflow.
- **Data Limite**: Data máxima para a conclusão do workflow.
- **Data Criação**: Data em que o workflow foi criado.
- **Última Atualização**: Data da última modificação no workflow.
- **IdWorkflowType**: Identificador do tipo de workflow ao qual pertence.
- **Status**: Estado atual do workflow (Anulado, Em curso ou Concluído).

### WorkflowType
- **Id**: Identificador único do tipo de workflow.
- **Nome**: Nome do tipo de workflow.
- **Descrição**: Breve descrição sobre o tipo de workflow.
- **Ativo**: Indica se o tipo de workflow está ativo.

### WorkflowTypeStep
- **Id**: Identificador único da etapa do tipo de workflow.
- **IdWorkflowType**: Identificador do tipo de workflow ao qual pertence.
- **Descrição**: Descrição da etapa.
- **Ativo**: Indica se a etapa está ativa.

### WorkflowSequence
- **Id**: Identificador único da sequência.
- **IdWorkflowTypeStepCurrent**: Identificador da etapa atual do tipo de workflow.
- **IdWorkflowTypeStepNext**: Identificador da próxima etapa do tipo de workflow.
- **IdWorkflowType**: Identificador do tipo de workflow ao qual pertence.
- **Ordem**: Ordem da sequência dentro do workflow.
- **Ativo**: Indica se a sequência está ativa.

### WorkflowHistory
- **Id**: Identificador único do histórico.
- **IdWorkflowTypeStepCurrent**: Identificador da etapa atual do tipo de workflow.
- **IdWorkflowTypeStepNext**: Identificador da próxima etapa do tipo de workflow.
- **IdWorkflow**: Identificador do workflow ao qual pertence.
- **Parâmetros Criador**: Informações sobre quem criou o histórico.
- **Parâmetro Execução**: Detalhes da execução do histórico.
- **User ID**: Identificador do usuário responsável pela ação.
- **Descrição**: Breve descrição da ação registrada no histórico.
- **Data Execução**: Data em que a ação foi realizada.
- **Data Criação**: Data em que o histórico foi criado.
- **Status**: Estado do workflow no momento do registro.

### WorkflowExecution
- **Id**: Identificador único da execução.
- **IdWorkflowTypeStepCurrent**: Identificador da etapa atual do tipo de workflow.
- **IdWorkflowTypeStepNext**: Identificador da próxima etapa do tipo de workflow.
- **IdWorkflow**: Identificador do workflow ao qual pertence.
- **Ordem**: Ordem da execução dentro do workflow.
- **Parâmetros Criador**: Informções sobre quem criou a execução.
- **Parâmetro Execução**: Detalhes da execução.
- **User ID**: Identificador do usuário responsável pela execução.
- **Descrição**: Breve descrição da execução.
- **Data Execução**: Data em que a execução foi realizada.
- **Data Criação**: Data em que a execução foi criada.
- **Ativo**: Indica se a execução está ativa.
- **Status**: Estado da execução no workflow.
- **IsLocked**: Indica se a execução está bloqueada.

![image](https://github.com/user-attachments/assets/9242e4f6-956e-410f-8982-e0a378fef351)
