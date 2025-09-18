# Dicionário de Dados (datasets de desafio)

## transacoes.csv
- **id_transacao** (string): Identificador único da transação.
- **conta_origem** (string): Conta de origem.
- **conta_destino** (string): Conta de destino.
- **valor** (float): Valor em reais (R$).
- **aprovacao_IA** (string): Se a IA aprovou automaticamente (`SIM`/`NAO`).
- **flag_controle_manual** (string): Se houve controle manual humano (`SIM`/`NAO`).
- **descricao** (string): Descrição/categoria da transação.
- **data_hora** (timestamp): Data e hora da transação.

Notas: 
- Existem **outliers** e **transações fracionadas** (smurfing) intencionais.
- Há casos em que `valor > 50.000` não possuem `flag_controle_manual = SIM` (violações para análise).

## logs_ia.csv
- **timestamp** (timestamp): Data e hora da interação com a IA.
- **usuario** (string): Identificador do usuário.
- **entrada_usuario** (string): Prompt inserido pelo usuário (pode conter tentativas de *prompt injection*).
- **resposta_IA** (string): Resposta gerada pela IA.
- **categoria** (string): Categoria da interação (ex.: `Dúvida Operacional`, `Suporte TI`, `Outro`).
- **acao_executada** (string): Ação tomada (`Nenhuma`, `Registro criado`, `Escalonamento`).
- **avaliacao** (string): Avaliação humana (`OK`/`FALHA`).

Notas:
- Existem tentativas de **jailbreak/prompt injection**.
- Foi induzida uma **tendência de aumento de FALHA** nos últimos 30 dias para simular **drift**.
