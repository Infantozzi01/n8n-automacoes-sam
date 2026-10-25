# Desafio Criativo: Planejando Automações com n8n

Passo 1: Defina a automação desejada

Quero criar uma automação no n8n para verificar e adicionar automaticamente novos moradores (proprietários e inquilinos) em uma lista de transmissão de comunicados do condomínio.

Público ou responsável:
Equipe do SAM (Serviço de Atendimento ao Morador).

Resultado esperado:
Inclusão automática dos moradores não adicionados na lista (analisando os cadastros dos últimos 6 meses) e, posteriormente, a inclusão imediata a cada novo registro feito no sistema.

---

Passo 2: Adicione contexto e regras

Ferramentas envolvidas:
Sistema de Gestão do Condomínio (via API ou Banco de Dados), API do WhatsApp (ex: Evolution API ou Z-API) e n8n.

Fluxo desejado:
1. Buscar os moradores cadastrados no sistema do condomínio (varredura retroativa de 6 meses e gatilho para novos cadastros).
2. Consultar os participantes atuais da lista de transmissão oficial do WhatsApp.
3. Cruzar os dados (Merge) para identificar quais moradores do sistema não estão na lista de transmissão.
4. Adicionar os números faltantes automaticamente à lista.
5. Enviar uma notificação de log/resumo para a equipe do SAM confirmando quem foi adicionado com sucesso.

Regras importantes:
- Filtrar e incluir apenas moradores com status ativo (excluindo ex-inquilinos ou ex-proprietários).
- Validar se o número de telefone possui o formato correto e contém o DDD.
- Ignorar registros sem número de celular preenchido.
- Garantir que não haja tentativa de inserção duplicada.

---

Passo 3: Monte o prompt final

Atue como um especialista em n8n.
Crie uma automação para automatizar a verificação e inclusão de novos moradores (proprietários e inquilinos) em uma lista de transmissão de comunicados do condomínio.

Público:
Equipe do SAM (Serviço de Atendimento ao Morador).

Ferramentas envolvidas:
Sistema de Gestão do Condomínio (API/Banco de Dados), API do WhatsApp e n8n.

Fluxo:
1. Buscar os cadastros de moradores no sistema (com opção de varredura retroativa de 6 meses ou via gatilho de novo cadastro).
2. Consultar os números que já compõem a lista de transmissão atual.
3. Cruzar os dados para identificar moradores cadastrados que não estão na lista de transmissão.
4. Adicionar os moradores faltantes à lista de transmissão do WhatsApp.
5. Enviar uma mensagem de confirmação para o WhatsApp ou e-mail do SAM com o nome de quem foi adicionado.

Regras:
- Incluir apenas moradores com status de "Proprietário" ou "Inquilino" ativo.
- Ignorar cadastros sem telefone ou com números em formatos inválidos.
- Realizar a checagem para evitar qualquer duplicidade de cadastro na lista.

Explique quais nós do n8n devem ser utilizados e a lógica de funcionamento do workflow.