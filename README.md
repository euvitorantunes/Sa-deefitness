# Sistema de Gerenciamento de Academia

Este repositório contém os scripts SQL para criar e popular um banco de dados Oracle para um sistema de gerenciamento de academia.

## Estrutura do Banco de Dados

### Tabelas

1. **USR_FITNESS.MEMBROS**
   - Armazena informações dos membros da academia
   - Campos: MEMBRO_ID, NOME, DATA_NASCIMENTO, TELEFONE, EMAIL

2. **USR_FITNESS.PLANOS_TREINAMENTO**
   - Contém os diferentes planos de treinamento disponíveis
   - Campos: PLANO_ID, NOME, DESCRICAO, DURACAO_SEMANAS

3. **USR_FITNESS.EXERCICIOS**
   - Cadastro de exercícios disponíveis
   - Campos: EXERCICIO_ID, NOME, TIPO, DESCRICAO

4. **USR_FITNESS.HISTORICO_TREINAMENTO**
   - Registra o histórico de treinamentos dos membros
   - Campos: HISTORICO_ID, MEMBRO_ID, PLANO_ID, DATA_INICIO, DATA_FIM, STATUS

5. **USR_FITNESS.ROTINAS_TREINAMENTO**
   - Define as rotinas de exercícios para cada plano
   - Campos: ROTINA_ID, PLANO_ID, EXERCICIO_ID, SERIES, REPETICOES, DESCANSO_SEGUNDOS

### Relacionamentos

- Um MEMBRO pode ter vários HISTORICOS_TREINAMENTO
- Um PLANO_TREINAMENTO pode estar em vários HISTORICOS_TREINAMENTO
- Um PLANO_TREINAMENTO pode ter várias ROTINAS_TREINAMENTO
- Um EXERCICIO pode estar em várias ROTINAS_TREINAMENTO

## Como Executar os Scripts

1. Conecte-se ao Oracle SQL*Plus ou SQL Developer como usuário com privilégios adequados

2. Execute o script de estrutura:
   ```sql
   @estrutura.sql
   ```

3. Execute o script de dados:
   ```sql
   @dados.sql
   ```

## Objetivo do Banco de Dados

Este banco de dados foi projetado para gerenciar uma academia de ginástica, permitindo:
- Cadastro e gestão de membros
- Gerenciamento de planos de treinamento
- Controle de exercícios
- Acompanhamento do histórico de treinamento dos membros
- Definição de rotinas de exercícios específicas para cada plano
